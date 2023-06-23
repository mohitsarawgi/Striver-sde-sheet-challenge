#include<bits/stdc++.h>

TreeNode<int> *constructTree(int is, int ie, vector<int> &inorder, int ps,
                             int pe, vector<int> &postorder,
                             unordered_map<int, int> &mp) {
  if (ps > pe or is > ie)
    return NULL;

  TreeNode<int> *root = new TreeNode<int>(postorder[pe]);
  int inroot = mp[root->data];
  int numsLeft = inroot - is;

  root->left = constructTree(is, inroot - 1, inorder, ps, ps + numsLeft - 1,
                             postorder, mp);
  root->right = constructTree(inroot + 1, ie, inorder, ps + numsLeft, pe - 1,
                              postorder, mp);

  return root;
}

TreeNode<int> *getTreeFromPostorderAndInorder(vector<int> &postorder, vector<int> &inorder) {
  unordered_map<int, int> mp;
  for (int i = 0; i < inorder.size(); i++)
    mp[inorder[i]] = i;

  return constructTree(0, inorder.size() - 1, inorder, 0, postorder.size() - 1,
                       postorder, mp);
}
