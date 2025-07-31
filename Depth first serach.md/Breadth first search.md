## 01. BASIC TREE STRUCTURE

````java[]
package TREES;
import java.util.*;
class Node{
	int data;
	Node left;
	Node right;
	Node(int value){
		data = value;
		left = null;
		right = null;
	}
}
public class Example1 {	
	public static void main(String[] args) {
		Node root = new Node(2);
		Node node1 = new Node(3);
		Node node2 = new Node(7);
		root.left = node1;
		root.right = node2;
		System.out.println(root.data);
		System.out.println(root.left.data);
		System.out.println(root.right.data);
	}

}

````

## 02. INORDER TRAVERSAL

````java[]


package TREES;
import java.util.*;
class Node{
	int data;
	Node left;
	Node right;
	Node(int value){
		data = value;
		left = null;
		right = null;
	}
}
public class Example1 {	
	public static void inorder(Node node) {
        if (node == null)
            return;
        
        inorder(node.left);
        System.out.print(node.data + " ");
        inorder(node.right);
    }
	public static void main(String[] args) {
		Node root = new Node(3);
        Node node1 = new Node(7);
        Node node2 = new Node(9);
        
        root.left = node1;
        root.right = node2;	
        node1.left = new Node(13);
        node1.right = new Node(4);
        
        node1.left.right = new Node(2);
        node1.right.left = new Node(1);
        node1.right.right = new Node(8);
        inorder(root);
	}

}
OUTPUT:
13 2 7 1 4 8 3 9
````

## 03. PREORDER AND POSTORDER 

````java[]
PRE & POSTORDER

package TREES;
import java.util.*;
class Node{
	int data;
	Node left;
	Node right;
	Node(int value){
		data = value;
		left = null;
		right = null;
	}
}
public class Example1 {	
	public static void inorder(Node node) {
        if (node == null)
            return;
        
        inorder(node.left);
        System.out.print(node.data + " ");
        inorder(node.right);
    }
	public static void preorder(Node node) {
		if(node == null)
			return;
		System.out.print(node.data + " ");
		preorder(node.left);
		preorder(node.right);
	}
	
	public static void postorder(Node node) {
		if(node == null)
			return;
		
		postorder(node.left);
		postorder(node.right);
		System.out.print(node.data + " ");
		
	}
	public static void main(String[] args) {
		Node root = new Node(3);
        Node node1 = new Node(7);
        Node node2 = new Node(9);
        
        root.left = node1;
        root.right = node2;	
        node1.left = new Node(13);
        node1.right = new Node(4);
        
        node1.left.right = new Node(2);
        node1.right.left = new Node(1);
        node1.right.right = new Node(8);
        
        System.out.print("Inorder Traversal:");
        inorder(root);
        System.out.println();
        
        System.out.print("Preorder Traversal:");
        preorder(root);
        System.out.println();
        
        System.out.print("Postorder Traversal:");
        postorder(root);
	}

}

OUTPUT:
Inorder Traversal:13 2 7 1 4 8 3 9 
Preorder Traversal:3 7 13 2 4 1 8 9 
Postorder Traversal:2 13 1 8 4 7 9 3 

````

## 01. LEVELORDER TRAVERSAL

````java[]

package TREES;
import java.util.*;
class Node{
	int data;
	Node left;
	Node right;
	Node(int value){
		data = value;
		left = null;
		right = null;
	}
}
public class Example2 {
	public static void inorder(Node node) {
        if (node == null)
            return;
        
        inorder(node.left);
        System.out.print(node.data + " ");
        inorder(node.right);
    }
	 public static void levelOrder(Node root) {
	        if (root == null)
	            return;

	        Queue<Node> queue = new LinkedList<>();
	        queue.add(root);

	        while (!queue.isEmpty()) {
	            Node current = queue.poll(); 
	            System.out.print(current.data + " ");

	            if (current.left != null)
	                queue.add(current.left);
	            if (current.right != null)
	                queue.add(current.right);
	        }
	    }
	public static void main(String[] args) {
		Node root = new Node(3);
        Node node1 = new Node(7);
        Node node2 = new Node(9);
        
        root.left = node1;
        root.right = node2;	
        node1.left = new Node(13);
        node1.right = new Node(4);
        
        node1.left.right = new Node(2);
        node1.right.left = new Node(1);
        node1.right.right = new Node(8);
        
        System.out.print("Inorder Traversal:");
        inorder(root);
        System.out.println();
        
        levelOrder(root);
	}

}
output:
Inorder Traversal:13 2 7 1 4 8 3 9 
3 7 9 13 4 2 1 8

````
