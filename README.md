# LINKED-LIST
//INSERT NODE AT i-th POSITION
//SOURCE CODE
import java.util.*;
import java.io.*;
public class Main{
    public static void main(String args[]){
        Scanner sc=new Scanner (System.in);
        LinkedList list=new LinkedList();
        while(true){
            int n=sc.nextInt();
            if(n<0){
                break;
            }
            else{
                list.insertAtEnd(n);
            }
            
        }
        int pos=sc.nextInt();
        int val=sc.nextInt();
        list.insertAtPos(pos,val);
        list.display();
    }
}
class LinkedList{
    Node head,tail;
    LinkedList(){
        head=null;
        tail=null;
    }
    class Node{
        int data;
        Node next;
        Node (int val){
            data=val;
            next=null;
        }
    }
    public void insertAtEnd(int val){
        Node n=new Node(val);
        if(head==null){
            head=n;
            tail=n;
        }
        else{
            tail.next=n;
            tail=n;
        }
    }
    public void insertAtPos(int pos,int val){
        Node n=new Node(val);
        if(pos==0){
            n.next=head;
            head=n;
            return;
        }
        Node temp=head;
        for (int i=1;i<pos;i++){
            temp=temp.next;
        }
        n.next=temp.next;
        temp.next=n;
    }
    public void display(){
        Node temp=head;
        while(temp!=null){
            System.out.print(temp.data+" ");
            temp=temp.next;
        }
    }
}
