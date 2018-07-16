# Java_EE_Udemy24
Differences between Singleton and Stateful Enterprise Java beans
For this tutorial I copied the CounterBean EJB and created a Stateful version called CounterStatefulBean
I imported both into the AddOne and ShowCount Servlets
AddOne:
    out.println("The current count value of the Singleton Bean is: " + cb.getCount());
		out.println("The current count value of the Stateful Bean is: " + cbStateful.getCount());

		
		cb.addOneToCount();
		cbStateful.addOneToCount();
		out.println("The count was incremented by one. The current count value for the Singleton Bean is: " + cb.getCount());
		
		
		out.println("The count was incremented by one. The current count value for the Stateful Bean is: " + cbStateful.getCount());
    
ShowCount:
    out.println("The count value is for the Singleton Bean is : " + cb.getCount());
		
		out.println("The counter value for the Stateful Bean is : " + cbStateful.getCount());
    
Again the AddOne Servlet added one to the counter each time the page was refreshed but when the page was changed to ShowCount the Stateful Bean 
returned to zero. This is because the Stateful Bean is creating a new object for each servlet whereas the Singleton keeps the same for both.
    
