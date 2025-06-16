class Node {
    int data;
    Node left, right;

    Node(int value) {
        data = value;
        left = right = null;
    }
}

public class maxDepthOfBinaryTree {
    Node root;

    // maxDepth method
    int maxDepth(Node node) {
        if (node == null) return 0;

        int leftDepth = maxDepth(node.left);
        int rightDepth = maxDepth(node.right);

        return Math.max(leftDepth, rightDepth) + 1;
    }

    public static void main(String[] args) {
        maxDepthOfBinaryTree tree = new maxDepthOfBinaryTree();

        tree.root = new Node(1);
        tree.root.left = new Node(2);
        tree.root.right = new Node(3);
        tree.root.left.left = new Node(4);
        tree.root.left.right = new Node(5);
        tree.root.left.left.left = new Node(6);

        int depth = tree.maxDepth(tree.root);
        System.out.println("Maximum depth of tree: " + depth);
    }
}
