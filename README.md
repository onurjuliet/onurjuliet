- 👋 Hi, I’m @onurjuliet
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
onurjuliet/onurjuliet is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->


package s200316071;
import java.util.Scanner;

public class S200316071 
{   
    public static void main(String[] args) 
    {
        Scanner sc = new Scanner(System.in);
        String decision_ff , decision_child , decision_vip , decision_day , decision_last;
        double price = 0;
        int person_count , last_person , extra_person , children , day;
        int twoRoom_count = 0 , threeRoom_count =0 , fourRoom_count = 0;
        int two_room =200 , three_room =170 , four_room =150;
        int rate = 0;       
        System.out.println("How many guests will stay at the hotel?");
        person_count = sc.nextInt();  
        last_person = person_count ;
        while ( person_count < 1 )
        {                 
           System.out.println("The number of person cannot be less than 1. Please re-enter.. ");
           System.out.println("How many guests will stay at the hotel?");
           person_count = sc.nextInt();
        }
        if(person_count == 1)
        {           
           price = two_room + 80 ;
           twoRoom_count +=1;
        }
        if(person_count > 1)
        {
           System.out.println("Are you a family or friends? Please short answer family or friends");
           decision_ff = sc.next();
           while(!decision_ff.toLowerCase().equals("family") && !decision_ff.toLowerCase().equals("friends"))
            {
                System.out.println("Something went wrong...");
                System.out.println("Please re-enter only 'family' or 'friends'");
                decision_ff = sc.next();          
            }
            if("friends".equals(decision_ff.toLowerCase()))
            {
                if(person_count == 2)
                {
                    price = person_count * two_room ;
                    twoRoom_count +=1;
                }
                else if(person_count ==3)
                {
                    price = person_count * three_room;
                    threeRoom_count +=1;
                }
                else if(person_count == 4)
                {
                    price = person_count * four_room;
                    fourRoom_count +=1;
                }
                else
                {
                    extra_person = person_count % 4;
                    person_count = person_count / 4;
                    fourRoom_count += person_count;  
                    price = (person_count * four_room )*4;                    
                    if(extra_person == 1)
                    {
                        price = price + (extra_person * two_room) + 80 ;
                        twoRoom_count +=1;
                    }
                    else if(extra_person == 2)
                    {
                        price = price + (extra_person * two_room) ;
                        twoRoom_count +=1;
                    }
                    else if(extra_person ==3)
                    {
                        price = price + (extra_person * three_room);
                        threeRoom_count +=1;
                    }
                }
            }
            else if("family".equals(decision_ff.toLowerCase()))
            {
                System.out.println("Do you have child? Please short answer 'yes' or 'no' ");
                decision_child = sc.next();
                while(!decision_child.toLowerCase().equals("yes") && !decision_child.toLowerCase().equals("no"))
                {
                    System.out.println("Something went wrong...");
                    System.out.println("Please re-enter only 'yes' or 'no'");
                    decision_child = sc.next(); 
                }
                if("yes".equals(decision_child.toLowerCase()))
                {
                    System.out.println("How many children do you have?");
                    children = sc.nextInt();
                    while(children <1)        
                    {
                        System.out.println("The number of children cannot be less than 1");            
                        System.out.println("How many children do you have?");
                        children = sc.nextInt();
                    }
                    if(children == 1)
                    {                          
                        if(person_count ==2)
                        {
                            price = ((person_count - children) * two_room ) + (two_room/2) * children ;
                            twoRoom_count +=1;
                        }
                        else if(person_count == 3)
                        {
                            price = ((person_count - children) * two_room ) + (two_room/2) * children ;
                            twoRoom_count +=1;
                        }
                        else if(person_count == 4 )
                        {
                            price = ((person_count - children) * three_room ) + (three_room/2) * children ;
                            threeRoom_count +=1;
                        }
                        else if(person_count == 5)
                        {
                            price = ((person_count - children) * four_room ) + (four_room/2) * children ;
                            fourRoom_count +=1;
                        }
                        else
                        {
                           extra_person = person_count % 4;
                           person_count = person_count / 4;
                           fourRoom_count += person_count ;
                           price = (person_count * four_room )*4;
                           if(extra_person == 1)
                           {
                               price = price + (extra_person*two_room) + 80 ;
                               twoRoom_count +=1;
                           }
                           else if(extra_person == 2)
                           {
                               price = price + (extra_person*two_room) ;
                               twoRoom_count +=1;
                           }
                           else if(extra_person ==3)
                           {
                               price = price + (extra_person * three_room);
                               threeRoom_count +=1;
                           }
                        }
                    }                    
                    else
                    {             
                        if(person_count == 3)
                        {
                            price = ((person_count - children) * two_room ) + ((two_room*75)/100 * children) ;
                            twoRoom_count +=1;
                        }
                        else if(person_count == 4)
                        {
                            price = ((person_count - children) * three_room ) + ((three_room*75)/100 * children) ;
                            threeRoom_count +=1;
                        }
                        else if(person_count == 5 )
                        {
                            price = ((person_count - children) * four_room ) + ((four_room*75)/100 * children) ;
                            fourRoom_count +=1;
                        }
                        else
                        {
                           extra_person = person_count % 4;
                           person_count = person_count / 4;
                           fourRoom_count += person_count ;
                           price = (person_count * four_room )*4;
                           if(extra_person == 1)
                           {
                               price = price + (extra_person * two_room) + 80 ;
                               twoRoom_count +=1;
                           }
                           else if(extra_person == 2)
                           {
                               price = price + (extra_person * two_room) ;
                               twoRoom_count+=1;
                           }
                           else if(extra_person ==3)
                           {
                               price = price + (extra_person * three_room);
                               threeRoom_count +=1;
                           }
                        }                       
                    }
                                                                         
                }
                else
                {                                                                       
                    if(person_count == 2)
                    {
                        price = person_count * two_room ;
                        twoRoom_count +=1;
                    }
                    else if(person_count ==3)
                    {
                        price = person_count * three_room;
                        threeRoom_count +=1;
                    }
                    else if(person_count == 4)
                    {
                        price = person_count * four_room;
                        fourRoom_count +=1;
                    }
                    else
                    {
                        extra_person = person_count % 4;
                        person_count = person_count / 4;
                        fourRoom_count += person_count;  
                        price = (person_count * four_room )*4;                    
                        if(extra_person == 1)
                        {
                            price = price + (extra_person * two_room) + 80 ;
                            twoRoom_count +=1;
                        }
                        else if(extra_person == 2)
                        {
                            price = price + (extra_person * two_room) ;
                            twoRoom_count +=1;
                        }
                        else if(extra_person ==3)
                        {   
                            price = price + (extra_person * three_room);
                            threeRoom_count +=1;
                        }
                    }                   
                }                          
            }           
        }
        System.out.println("Are you VIP member or not? Please short answer 'yes' or 'no'");
        decision_vip = sc.next();    
        while(!decision_vip.toLowerCase().equals("yes") && !decision_vip.toLowerCase().equals("no"))
        {
            System.out.println("Something went wrong...");
            System.out.println("Please re-enter only 'yes' or 'no'");
            decision_vip = sc.next(); 
        }
        if("yes".equals(decision_vip.toLowerCase()))
        {
            rate = rate + 5;                                  
        }            
        System.out.println("How many days will you stay?");
        day = sc.nextInt();
        while(day<1)
        {
            System.out.println("The number of day cannot be less than 1. Please re-enter.. ");
            System.out.println("How many day will you stay?");
            day = sc.nextInt();
        }
        if(day == 1 || day == 2 )
        {
            System.out.println("Will you stay weekdays or weekend? Please short answer only 'weekdays' or 'weekend'");
            decision_day = sc.next();
            while(!decision_day.toLowerCase().equals("weekdays") && !decision_day.toLowerCase().equals("weekend"))
            {
                System.out.println("Something went wrong...");
                System.out.println("Please re-enter only 'weekend' or 'weekdays'");
                decision_day = sc.next(); 
            }
            if(decision_day == "weekdays")
            {
                rate = rate + 3;               
            }                           
        }
        if(day >=4 && day<=7)
        {
            rate = rate + 4;                     
        }
        if(day > 7)
        {
            rate = rate + 6;
        }              
        System.out.println("Final price = " + price +". Would you like to make a reservation at this price? Please short answer 'yes' or 'no'");
        String last_decision = sc.next();
        while(!last_decision.toLowerCase().equals("yes") && !last_decision.toLowerCase().equals("no"))
        {
            System.out.println("Something went wrong...");
            System.out.println("Please re-enter only 'yes' or 'no'");
            System.out.println("Would you like to make a reservation at this price? Please short answer 'yes' or 'no'");
            last_decision = sc.next(); 
        }
        if("yes".equals(last_decision.toLowerCase()))
        {                    
            System.out.print("You booked ");
		if(fourRoom_count>0)
			System.out.printf(fourRoom_count + " 4-person room ");
		if(threeRoom_count>0)
			System.out.printf(threeRoom_count + " 3-person room ");
		if(twoRoom_count >0)
			System.out.printf(twoRoom_count + " 2-person room ");
		System.out.printf("for " + last_person +" guests for " + day + " days , with total cost of " + price);
        }
        else
        {
            System.out.println("Hope to see you again... Take care of yourself.");
        }      
    }
}
