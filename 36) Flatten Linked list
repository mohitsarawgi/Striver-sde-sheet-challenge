Node* merge(Node* head1, Node* head2)

{

    if(head1 == nullptr)

    {

        return head2;

    }

    if(head2 == nullptr)

    {

        return head1;

    }

 

    Node* ans = nullptr;

 

    if(head1->data <= head2->data)

    {

        ans = head1;

        ans->child = merge(head1->child , head2);

    }

    else

    {

        ans = head2;

        ans->child = merge(head1,head2->child);

    }

 

    return ans;

}

 

Node* flattenLinkedList(Node* head)

{

    if(head==nullptr || head->next == nullptr)

    {

        return head;

    }

 

          Node *newLL = flattenLinkedList(head->next);

 

          head->next = nullptr;

 

          Node *newHead = merge(newLL, head);

        

 

        return newHead;

}
