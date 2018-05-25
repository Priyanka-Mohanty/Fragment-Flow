# Fragment-Flow
Suppose ,A activity contains Fragment A,B,C,D and E .
The normal flow of open fragment is A->B->C->D->E.
And the flow of fragment,after click on the  back button : E->D->C->B->A.
If You want to go back from Fragment E->A ,or D->B,
To acheieve the above scenario, with the help of following these method :
#### fragmentTransaction.addToBackStack(null); 
#### fragmentManager.popBackStack(null,FragmentManager.POP_BACK_STACK_INCLUSIVE); 
#### fragmentManager.popBackStackImmediate(null,FragmentManager.POP_BACK_STACK_INCLUSIVE);


![](https://raw.githubusercontent.com/Priyanka-Mohanty/Fragment-Flow/master/20180525_215607.gif)

## If We want to move from Frgment E -> A ,Then these are the following code

MainActivity -> FragmentA

        FragmentManager fragmentManager = getSupportFragmentManager();
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
        FragmentA fragmentA = new FragmentA();
        fragmentManager.popBackStack(null,FragmentManager.POP_BACK_STACK_INCLUSIVE);
        fragmentTransaction.replace(R.id.fragment_content, fragmentA);
        fragmentTransaction.commit();
        
FragmentA -> FragmentB      

        FragmentManager fragmentManager = getActivity().getSupportFragmentManager();
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
        FragmentB fragmentB = new FragmentB();
        fragmentManager.popBackStack(null,FragmentManager.POP_BACK_STACK_INCLUSIVE);
        fragmentTransaction.replace(R.id.fragment_content, fragmentB);
        fragmentTransaction.addToBackStack(null);
        fragmentTransaction.commit();

FragmentB-> FragmentC

        FragmentManager fragmentManager = getActivity().getSupportFragmentManager();
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
        FragmentD fragmentD = new FragmentD();
        fragmentManager.popBackStack(null,FragmentManager.POP_BACK_STACK_INCLUSIVE);
        fragmentTransaction.replace(R.id.fragment_content, fragmentD);
        fragmentTransaction.addToBackStack(null);
        fragmentTransaction.commit();

FragmentC-> FragmentD

        FragmentManager fragmentManager = getActivity().getSupportFragmentManager();
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
        FragmentD fragmentD = new FragmentD();
        fragmentManager.popBackStack(null,FragmentManager.POP_BACK_STACK_INCLUSIVE);
        fragmentTransaction.replace(R.id.fragment_content, fragmentD);
        fragmentTransaction.addToBackStack(null);
        fragmentTransaction.commit();
                
FragmentD-> FragmentE
  
        FragmentManager fragmentManager = getActivity().getSupportFragmentManager();
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
        FragmentE fragmentE = new FragmentE();
        fragmentManager.popBackStackImmediate(null,FragmentManager.POP_BACK_STACK_INCLUSIVE);
        fragmentTransaction.replace(R.id.fragment_content, fragmentE);
        fragmentTransaction.addToBackStack(null);
        fragmentTransaction.commit();
        
## If We want to move from Frgment E -> B ,Then these are the following code

MainActivity -> FragmentA

        FragmentManager fragmentManager = getSupportFragmentManager();
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
        FragmentA fragmentA = new FragmentA();
        fragmentManager.popBackStack(null,FragmentManager.POP_BACK_STACK_INCLUSIVE);
        fragmentTransaction.replace(R.id.fragment_content, fragmentA);
        fragmentTransaction.commit();
        
FragmentA -> FragmentB      

        FragmentManager fragmentManager = getActivity().getSupportFragmentManager();
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
        FragmentB fragmentB = new FragmentB();
        fragmentManager.popBackStack(null,FragmentManager.POP_BACK_STACK_INCLUSIVE);
        fragmentTransaction.replace(R.id.fragment_content, fragmentB);
        fragmentTransaction.commit();

FragmentB-> FragmentC

        FragmentManager fragmentManager = getActivity().getSupportFragmentManager();
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
        FragmentD fragmentD = new FragmentD();
        fragmentManager.popBackStack(null,FragmentManager.POP_BACK_STACK_INCLUSIVE);
        fragmentTransaction.replace(R.id.fragment_content, fragmentD);
        fragmentTransaction.addToBackStack(null);
        fragmentTransaction.commit();

FragmentC-> FragmentD

        FragmentManager fragmentManager = getActivity().getSupportFragmentManager();
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
        FragmentD fragmentD = new FragmentD();
        fragmentManager.popBackStack(null,FragmentManager.POP_BACK_STACK_INCLUSIVE);
        fragmentTransaction.replace(R.id.fragment_content, fragmentD);
        fragmentTransaction.addToBackStack(null);
        fragmentTransaction.commit();
                
FragmentD-> FragmentE
  
        FragmentManager fragmentManager = getActivity().getSupportFragmentManager();
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
        FragmentE fragmentE = new FragmentE();
        fragmentManager.popBackStackImmediate(null,FragmentManager.POP_BACK_STACK_INCLUSIVE);
        fragmentTransaction.replace(R.id.fragment_content, fragmentE);
        fragmentTransaction.addToBackStack(null);
        fragmentTransaction.commit();
        
## If We want to move from Frgment E -> D -> A ,Then these are the following code

MainActivity -> FragmentA

        FragmentManager fragmentManager = getSupportFragmentManager();
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
        FragmentA fragmentA = new FragmentA();
        fragmentManager.popBackStack(null,FragmentManager.POP_BACK_STACK_INCLUSIVE);
        fragmentTransaction.replace(R.id.fragment_content, fragmentA);
        fragmentTransaction.commit();
        
FragmentA -> FragmentB      

        FragmentManager fragmentManager = getActivity().getSupportFragmentManager();
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
        FragmentB fragmentB = new FragmentB();
        fragmentManager.popBackStack(null,FragmentManager.POP_BACK_STACK_INCLUSIVE);
        fragmentTransaction.replace(R.id.fragment_content, fragmentB);
        fragmentTransaction.addToBackStack(null);
        fragmentTransaction.commit();

FragmentB-> FragmentC

        FragmentManager fragmentManager = getActivity().getSupportFragmentManager();
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
        FragmentD fragmentD = new FragmentD();
        fragmentManager.popBackStack(null,FragmentManager.POP_BACK_STACK_INCLUSIVE);
        fragmentTransaction.replace(R.id.fragment_content, fragmentD);
        fragmentTransaction.addToBackStack(null);
        fragmentTransaction.commit();

FragmentC-> FragmentD

        FragmentManager fragmentManager = getActivity().getSupportFragmentManager();
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
        FragmentD fragmentD = new FragmentD();
        fragmentManager.popBackStackImmediate(null,FragmentManager.POP_BACK_STACK_INCLUSIVE);
        fragmentTransaction.replace(R.id.fragment_content, fragmentD);
        fragmentTransaction.addToBackStack(null);
        fragmentTransaction.commit();
                
FragmentD-> FragmentE
  
        FragmentManager fragmentManager = getActivity().getSupportFragmentManager();
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
        FragmentE fragmentE = new FragmentE();
        fragmentTransaction.replace(R.id.fragment_content, fragmentE);
        fragmentTransaction.addToBackStack(null);
        fragmentTransaction.commit();
        
## If We want to move from Frgment E -> D -> B or D-> B ,Then these are the following code

MainActivity -> FragmentA

        FragmentManager fragmentManager = getSupportFragmentManager();
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
        FragmentA fragmentA = new FragmentA();
        fragmentManager.popBackStack(null,FragmentManager.POP_BACK_STACK_INCLUSIVE);
        fragmentTransaction.replace(R.id.fragment_content, fragmentA);
        fragmentTransaction.commit();
        
FragmentA -> FragmentB      

        FragmentManager fragmentManager = getActivity().getSupportFragmentManager();
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
        FragmentB fragmentB = new FragmentB();
        fragmentManager.popBackStack(null,FragmentManager.POP_BACK_STACK_INCLUSIVE);
        fragmentTransaction.replace(R.id.fragment_content, fragmentB);
        fragmentTransaction.commit();

FragmentB-> FragmentC

        FragmentManager fragmentManager = getActivity().getSupportFragmentManager();
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
        FragmentD fragmentD = new FragmentD();
        fragmentManager.popBackStack(null,FragmentManager.POP_BACK_STACK_INCLUSIVE);
        fragmentTransaction.replace(R.id.fragment_content, fragmentD);
        fragmentTransaction.addToBackStack(null);
        fragmentTransaction.commit();

FragmentC-> FragmentD

        FragmentManager fragmentManager = getActivity().getSupportFragmentManager();
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
        FragmentD fragmentD = new FragmentD();
        fragmentManager.popBackStackImmediate(null,FragmentManager.POP_BACK_STACK_INCLUSIVE);
        fragmentTransaction.replace(R.id.fragment_content, fragmentD);
        fragmentTransaction.addToBackStack(null);
        fragmentTransaction.commit();
                
FragmentD-> FragmentE
  
        FragmentManager fragmentManager = getActivity().getSupportFragmentManager();
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();
        FragmentE fragmentE = new FragmentE();
        fragmentTransaction.replace(R.id.fragment_content, fragmentE);
        fragmentTransaction.addToBackStack(null);
        fragmentTransaction.commit();
