/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    vector<int> preorderTraversal(TreeNode* root) {
        vector<int> result;
        preorder(root, result); // Helper function to perform the traversal
        return result;
    }
    
    // Helper function to perform preorder traversal recursively
    void preorder(TreeNode* node, vector<int>& result) {
        if (node == nullptr) {
            return; // Base case: if node is null, return
        }
        result.push_back(node->val); // Visit the root node
        preorder(node->left, result); // Traverse the left subtree
        preorder(node->right, result); // Traverse the right subtree
    }
};
