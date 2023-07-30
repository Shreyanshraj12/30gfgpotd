# 30gfgpotd
class Solution{
  public:
    // returns the inorder successor of the Node x in BST (rooted at 'root')
    Node* ans = new Node(-1);
    int flag = 0;
    void solve(Node* root, Node* x){
        if(root == NULL)
            return;
        solve(root -> left, x);
        if(flag == 1){
            ans = root;
            flag = -1;
        }
        if(flag == 0 && x == root)
            flag = 1;
        solve(root -> right, x);
    }
    
    Node * inOrderSuccessor(Node *root, Node *x)
    {
        solve(root, x);
        return ans;
    }
};
