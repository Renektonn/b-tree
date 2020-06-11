static void input(int quantity){
    Scanner cin=new Scanner(System.in);
    Node tem,head,tail;
    tem=new Node(cin.nextInt());
    head=tem;

    for(int i=0;i<quantity-1;i++){
      tem=new Node(cin.nextInt());
      tail=head; //error
      if(tem.data<tail.data){ 
        if(tail.left==null){
          tail.left=tem;
        }
        else{
          tail=tail.left;
        }
      } 
      if(tem.data>tail.data){ 
        if(tail.right==null){
          tail.right=tem;
        }
        else{
          tail=tail.right;
        }
      }
    }
    output(head); 
  }
  static void output(Node head) {
		Node tem=head;
		if(tem!=null) {
			System.out.print(tem.data+" ");
			output(tem.left);
			output(tem.right);
		}
	}
