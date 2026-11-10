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

# REVERSE A DLL
def reverseDLL(self, head):
        if head is None:
            return 
        curr=head
        while curr:
            curr.prev,curr.next=curr.next,curr.prev
            head=curr
            curr=curr.prev
        return head

# DELETE Kth element
def deleteKthElement(head, k):
    if head is None:
        return None
    if k == 1:
        return head.next
    curr = head
    for i in range(1, k - 1):
        curr = curr.next
        if curr is None:
            return head
    if curr.next:
        curr.next = curr.next.next
    return head

# INSERT A NODE BEFORE TAIL
 def insertBeforeTail(self, head: ListNode, X: int) -> ListNode:
        newNode=ListNode(X)
        if head is None:
            return 
        curr=head
        while curr.next is not None:
            curr=curr.next
        newNode.prev=curr.prev
        newNode.next=curr
        if curr.prev:
            curr.prev.next=newNode    #Establishing forward connection 
        else: 
            head=newNode
        curr.prev=newNode
        return head

# INSERT BEFORE GIVEN NODE
def insertBeforeGivenNode(self, node: ListNode, X: int) -> None:
        if node is None:
            return 
        newnode=ListNode(X)
        newnode.prev=node.prev
        newnode.next=node
        if node.prev:
            node.prev.next=newnode
        node.prev=newnode


# SEGGERATE ODD EVEN NODES IN A LINKEDLIST
if head is None and head.next is None:
            return head
        odd=head
        even=head.next
        evenhead=even
        while even and even.next:
            odd.next=even.next
            odd=odd.next
            even.next=odd.next
            even=even.next
        odd.next=evenhead
        return head

