public class Ice_task_03 {

    public static void main(String[] args) {
        LibraryBook b1=new LibraryBook("Java Programming",2,0,10.00);
        double lateFees;
        boolean bookborrowed;
        boolean bookReturned;
        
        
        bookborrowed=b1.borrowBook();
        if (bookborrowed){
            System.out.println("successful");
            
        }else{
            System.out.println("unsuccessful");
        }
        
        
        bookReturned=b1.returnBook();
        if (bookReturned){
            System.out.println("successful");
            
        }else{
            System.out.println("unsuccessful");
        }
        
        lateFees=b1.calculateLateFee(3);
        System.out.println("Late fees: R"+lateFees);

        }
        }

        

public class LibraryBook {
    private String title;
    private int totalCopies;
    private int borrowedCopies;
    private double pricePerDayLate;
    
    public LibraryBook(String title,int totalCopies,int borrowedCopies,double pricePerDayLate){
        this.title=title;
        this.totalCopies=totalCopies;
        this.borrowedCopies=0;
        this.pricePerDayLate=pricePerDayLate;
                
    }
    
    public boolean isAvailable(){
        return(totalCopies - borrowedCopies>0);
    }
    
    public boolean borrowBook(){
        if (isAvailable()){
            borrowedCopies+=1;
            return true;
        }
        else{
                    
            return false;
        }    
        
    }
  public boolean returnBook(){
        if(borrowBook()){
            borrowedCopies-=1;
            return true;
        }
        else{
            return false;
        }
    }
    
    public double calculateLateFee(int daysLate){
        return daysLate*pricePerDayLate;
    }
    
}



public class LibraryBookTest {
    
    public LibraryBookTest() {
    }

    @Test
    public void testIsAvailable() {
        
        LibraryBook b1=new LibraryBook("Java Programming",2,0,10.00);
        boolean expected = true;
      
        boolean actual = b1.isAvailable();      
        Assertions.assertEquals(expected, actual);
    }
    @Test
    public void testIsAvailableTrue() {
        LibraryBook b1=new LibraryBook("Java Programming",2,0,10.00);
        boolean condition = b1.isAvailable();
        Assertions.assertTrue(condition);
        
    }
    @Test
    public void testIsAvailableFalse() {
        LibraryBook b1=new LibraryBook("Java Programming",0,0,10.00);
        boolean condition = b1.isAvailable();
        Assertions.assertFalse(condition);
        
    }

@Test
    public void testBorrowBook() {
        LibraryBook b1=new LibraryBook("Java Programming",2,0,10.00);
        boolean expected = true;
      
        boolean actual = b1.borrowBook();      
        Assertions.assertEquals(expected, actual);
        
    }
    
    @Test
    public void testBorrowBookTrue() {
          
        LibraryBook b1=new LibraryBook("Java Programming",2,0,10.00);
        boolean condition = b1.borrowBook();
        Assertions.assertTrue(condition);
        
    }
    @Test
    public void testBorrowBookFalse() {
          
        LibraryBook b1=new LibraryBook("Java Programming",0,0,10.00);
        boolean condition = b1.borrowBook();
        Assertions.assertFalse(condition);
        
    }

  @Test
    public void testReturnBook() {
        LibraryBook b1=new LibraryBook("Java Programming",2,0,10.00);
        boolean expected = true;
      
        boolean actual = b1.returnBook();      
        Assertions.assertEquals(expected, actual);
    }
    
    @Test
    public void testReturnBookTrue() {
          
        LibraryBook b1=new LibraryBook("Java Programming",2,0,10.00);
        boolean condition = b1.returnBook();
        Assertions.assertTrue(condition);
        
    }
    @Test
    public void testReturnBookFalse() {
          
        LibraryBook b1=new LibraryBook("Java Programming",0,0,10.00);
        boolean condition = b1.returnBook();
        Assertions.assertFalse(condition);
        
    }
 @Test
    public void testCalculateFees(){
        
        LibraryBook b1=new LibraryBook("Java Programming",2,0,10.00);
        double expected=30.00;
   
      
        double condition = b1.calculateLateFee(3);      
        Assertions.assertEquals(expected, condition);
        
        
        
    }

   
}
