# dsq3import java .util.*;

public class a3q3 {

    public class node

    {

        int element;

        node left;

        node right;

        

        public node(int e)

        {

            element = e;

        }

    }

    node root;

    public a3q3(){

        root = null;

    }

    

    public node insert(node temproot, int e)

    {

        if(temproot!=null)

        {

            if(e < temproot.element)

            {

                temproot.left = insert(temproot.left , e);

            }

            else if(e > temproot.element)

            {

                temproot.right = insert(temproot.right,e);

            }

        }

        else

        {

            node n = new node(e);

            temproot = n;

        }

        return temproot;

    }

    

    public void converseinorder(node temproot)

    {

        if(temproot != null)

        {

            inorder(temproot.right);

            System.out.println(temproot.element + " ");

            inorder(temproot.left);

        }

    }

    

    public void inorder(node temproot)

    {

        if(temproot != null)

        {

            inorder(temproot.left);

            System.out.println(temproot.element + " ");

            inorder(temproot.right);

        }

    }

    

    public void preorder(node temproot)

    {

        if(temproot != null)

        {

            System.out.println(temproot.element + " ");

            inorder(temproot.left);

            inorder(temproot.right);

        }

    }

    

    public void postorder(node temproot)

    {

        if(temproot != null)

        { 

            inorder(temproot.left);

            inorder(temproot.right);

            System.out.println(temproot.element + " ");

        }

    }

    

    public static void main(String[] args) {

        a3q3 ob = new a3q3();

            while(true)

            {

                char ch;

                Scanner input = new Scanner(System.in);

                

                System.out.println();

                System.out.println("\n1. Insert Into Binary tree");

                System.out.println("\n2. Converse Inorder Traversal");

                System.out.println("\n3. Inorder Traversal");

                System.out.println("\n4. Preorder Traversal");

                System.out.println("\n5. Postorder Traversal");

                System.out.println("\n6. Exit");

                System.out.println("Enter Your Choice: ");

                String s = input.next();

                ch = s.charAt(0);

                

                switch(ch)

                {

                    case 1:

                        System.out.println("Input The Number For Insert In Binary Tree");

                        int number = input.nextInt();

                        for(int i = 1; i <=number; i++)

                        {

                            System.out.println("Enter The Element for " + i);

                            int element = input.nextInt();

                            if(i == 1)

                            {

                                ob.root = ob.insert(ob.root,element);

                            }

                            else

                            {

                                ob.insert(ob.root, element);

                            }

                        }

                        break;

                        

                    case 2:

                        System.out.println("Converse In Order traversal");

                        ob.converseinorder(ob.root);

                        break;

                        

                    case 3:

                        System.out.println("Inorder Traversal");

                        ob.inorder(ob.root);

                        break;

                        

                    case 4:

                        System.out.println("Pre Traversal");

                        ob.preorder(ob.root);

                        break;

                        

                    case 5:

                        System.out.println("Post Traversal");

                        ob.postorder(ob.root);

                        break;

                        

                    case 6:

                        System.out.println("Exit");

                        break;

                        

                    default:

                        System.out.println("Invalid Choice");

                        break;

                }

            }

    }

}
