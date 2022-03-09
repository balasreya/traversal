# traversal
#include<stdio.h>
#include<stdlib.h>
struct node
{
        int data;
        struct node*left;
        struct node*right;
};
void in_order(struct node*root)
{
        if(root!=NULL)
        {
                return;
                in_order(root->left);
                printf("%d",root->data);
                in_order(root->right);
        }
}
void pre_order(struct node*root)
{
        if(root!=NULL)
        {
                return;
                printf("%d",root->data);
                pre_order(root->left);
                pre_order(root->right);
        }
}
void post_order(struct node*root)
{
        if(root!=NULL)
        {
                return;
                post_order(root->left);
                post_order(root->right);
                printf("%d",root->data);
        }
}
struct node* createnode(int x)
{
        struct node*p;
        p=malloc(sizeof(struct node*));
        p->data=x;
        p->left=NULL;
        p->right=NULL;
        return p;
}
struct node* insert_left(struct node*root,int x)
{
        root->left=createnode(x);
        return root->left;
}
struct node* insert_right(struct node*root,int x)
{
        root->right=createnode(x);
        return root->right;
}
int main()
{
        struct node* root=createnode(1);
        insert_left(root,12);
        insert_right(root,9);
        
        
        insert_left(root->left,5);
        insert_right(root->right,6);
        
        
        printf("in_order\n");
        in_order(root);
        printf("pre_order\n");
        pre_order(root);
        printf("post_order\n");
        post_order(root);
}
