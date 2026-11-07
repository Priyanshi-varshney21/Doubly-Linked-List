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

# DELETE AT THE BEGINNING
def deleteathead(head):
  if head is None:
    return 
  newHead=head.next
  if newHead:
    newHead.prev=None
  head.next=None

  return newHead

# DELETE THE TAIL NODE
def deleteAtTail (self, head):
  if head is None:
    return 
  if head.next is None:
    return
  curr=head
  while curr.next is not None:
    curr=curr.next
  curr.prev.next=None
  curr.prev = None
  return head

  # CONVERT ARRAY INTO LINKEDLIST
  def arrayToDoublyLinkedList(self, arr):
        if head is None:
            return 
        head=Node(arr[0])
        prev=head
        for i in range(1,len(arr)):
            newNode=Node(arr[i])
            prev.next=newNode
            newNode.prev=prev
            prev=newNode
        return head

# REMOVING GIVEN NODE IN A DOUBLY LL
def deleteGivenNode(self, node: ListNode) -> None:
        if node is None:
            return
        if node.prev:   #Remove forward connection
            node.prev.next=node.next
        if node.next:   #Remove backward connection
            node.next.prev=node.prev
        node.prev=None   #To completely disconnect the nodes
        node.next=None
