# DSA
class Node:
        def __init__(self, data):
            self.data = data
            self.next = None
    
    class SinglyLinkedList:
        def __init__(self):
            self.head = None
    
        def is_empty(self):
            return self.head is None
    
        def insert_at_beginning(self, data):
            new_node = Node(data)
            new_node.next = self.head
            self.head = new_node
    
        def insert_at_end(self, data):
            new_node = Node(data)
            if self.head is None:
                self.head = new_node
                return
            current = self.head
            while current.next:
                current = current.next
            current.next = new_node
    
        def delete(self, target):
            if self.head is not None and self.head.data == target:
                self.head = self.head.next
                return
            current = self.head
            while current and current.next:
                if current.next.data == target:
                    current.next = current.next.next
                    return
                current = current.next
    
        def display(self):
            current = self.head
            while current:
                print(current.data, end=" -> ")
                current = current.next
            print("None")
    
    # Example usage:
    linked_list = SinglyLinkedList()
    linked_list.insert_at_end(1)
    linked_list.insert_at_end(2)
    linked_list.insert_at_end(3)
    
    linked_list.display()  # Display the linked list
    
    linked_list.insert_at_beginning(0)  # Insert at the beginning
    linked_list.display()
    
    linked_list.insert_at_end(4)  # Insert at the end
    linked_list.display()
    
    linked_list.delete(2)  # Delete an element
    linked_list.display()
