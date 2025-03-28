# validate_bstree   
class Solution {
public:
    void inOrder(TreeNode* root,TreeNode* &prev,bool &flag){
        if(root==NULL) return;
        inOrder(root->left,prev,flag);
        if(prev!=NULL){
            if(root->val <= prev->val){
                flag = false;
                return;
            }
        }
        prev = root;
        inOrder(root->right,prev,flag);
    }
    bool isValidBST(TreeNode* root) {
        TreeNode* prev = NULL;
        bool flag = true;
        inOrder(root,prev,flag);
        return flag;
    }
};
