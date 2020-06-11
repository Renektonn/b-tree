import java.util.Scanner;
class Main {
  public static void main(String[] args) {
    input(10);
  }
  static void input(int quantity){
    Scanner cin=new Scanner(System.in);
    Node tem,head,tail;
    tem=new Node(cin.nextInt());
    head=tem;
    for(int i=0;i<quantity-1;i++){
      tem=new Node(cin.nextInt());
      tail=head;
      while(true){  
        if(tem.data<tail.data){ 
          if(tail.left==null){
            tail.left=tem;
            break;
          }
          else{
            tail=tail.left;
          }
        } 
        if(tem.data>tail.data){ 
          if(tail.right==null){
            tail.right=tem;
            break;
          }
          else{
            tail=tail.right;
          }
        }
      }
    }  
    output(head); 
  }
  static void output(Node tail) {
		Node tem=tail;
		if(tem!=null) {
			System.out.print(tem.data+" ");
			output(tem.left);
			output(tem.right);
		}
	}
}
class Node{
  int data;
  Node left;
  Node right;
  Node(int data){
    this.data=data;
  }
}
