Introduction
In this tutorial, we will explore the linked list data structure and how to implement it in C#. A linked list is a sequence of nodes where each node
contains data and a reference (or link) to the next node in the sequence. Linked lists are dynamic data structures, meaning they can grow and 
shrink in size as needed, making them more flexible than arrays.

Types of Linked Lists
Singly Linked List: Each node points to the next node in the sequence.
Doubly Linked List: Each node points to both the next and the previous node.
Circular Linked List: The last node points back to the first node, forming a circle.
In this tutorial, we will focus on implementing a singly linked list in C#.

Implementing a Singly Linked List in C#
Node Class
First, we need to create a Node class that will represent each element in the linked list.
public class Node
{
    public int Data { get; set; }
    public Node Next { get; set; }

    public Node(int data)
    {
        Data = data;
        Next = null;
    }
}

LinkedList Class
Next, we will create the LinkedList class to manage the nodes.
public class LinkedList
{
    private Node head;

    public LinkedList()
    {
        head = null;
    }
    public void Append(int data)
    {
        Node newNode = new Node(data);
        if (head == null)
        {
            head = newNode;
            return;
        }
        Node current = head;
        while (current.Next != null)
        {
            current = current.Next;
        }
        current.Next = newNode;
    }
    public void Prepend(int data)
    {
        Node newNode = new Node(data)
        {
            Next = head
        };
        head = newNode;
    }
    public void Delete(int data)
    {
        if (head == null) return;

        if (head.Data == data)
        {
            head = head.Next;
            return;
        }

        Node current = head;
        while (current.Next != null && current.Next.Data != data)
        {
            current = current.Next;
        }

        if (current.Next != null)
        {
            current.Next = current.Next.Next;
        }
    }
    public void PrintList()
    {
        Node current = head;
        while (current != null)
        {
            Console.Write(current.Data + " -> ");
            current = current.Next;
        }
        Console.WriteLine("null");
    }
}
Main Program
Let's create a simple program to test our linked list implementation.
class Program
{
    static void Main(string[] args)
    {
        LinkedList list = new LinkedList();

        list.Append(10);
        list.Append(20);
        list.Append(30);
        list.PrintList();

        list.Prepend(5);
        list.PrintList(); 

        list.Delete(20);
        list.PrintList();
    }
}

Explanation
Append: Adds a new node at the end of the list.
Prepend: Adds a new node at the beginning of the list.
Delete: Removes a node with a specified value from the list.
PrintList: Displays the elements of the list in sequence.
Conclusion
You have now learned how to implement a basic singly linked list in C#. This data structure is fundamental and serves
as the building block for more complex data structures and algorithms. Practice adding more functionalities, such as finding a node,
reversing the list, and sorting the list to deepen your understanding.
