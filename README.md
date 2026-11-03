# Doubly-Linked-List

# INSERT AT HEAD
def insert_at_head(head,val):
  newnode=ListNode(val)
  if head is None:
    return newnode
  newnode.next=head
  head.prev=newnode
  return newnode

# INSERTION AT THE TAIL
def insertAtTail(head, val):
    newNode = Node(val)
    if head is None:
        return newNode
    curr = head
    while curr.next is not None:
        curr = curr.next
    curr.next = newNode
    newNode.prev = curr
    return head
