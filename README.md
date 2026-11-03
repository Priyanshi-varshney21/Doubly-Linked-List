# Doubly-Linked-List

# INSERT AT HEAD
def insert_at_head(head,val):
  newnode=ListNode(val)
  if head is None:
    return newnode
  newnode.next=head
  head.prev=newnode
  return newnode
