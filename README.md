# Асс-1
#include <iostream>
 
 // сумма
 
 int add( int x, int y )
 
 {
 
     if( y == 0 )
     
        return x;
        
     else
     
        return add( x ^ y, (x & y) << 1 );
        
 }
 
 // разность
 
 int subtr( int x, int y )
 
 {
 
    returnadd( x, -y );
    
 }
 
 // произведение
 
 int mult( int x, int y )
 
 {
 
     if( y == 0 )
     
        return 0;
        
     if ( y> 0 )
     
        return ( x + mult( x, subtr( y, 1 ) ) );
        
     if ( y< 0 )
     
    return -mult( x, -y );
    
 }
 
 
 // целочисленное деление
 
 int _div( int x, int y )
 
 {
   int sign = ( (x < 0) ^ (y < 0) ) ? -1 : 1;
   
   x = std::abs( x );
   
   y = std::abs( y );
   
   int q = 0;
   
       while( x>= y )
       
       {
       
          x = subtr( x, y );
          
          q = add( q, 1 );
          
       }
       
   return sign * q;
   
 }
 
 
 int main()
 
 {
 
   int a = 100;
   
   int b = 15;
   
   std::cout<< a << " + " << b << " = " << add  ( a, b ) << "\n";
   
   std::cout<< a << " - " << b << " = " <<subtr( a, b ) << "\n";
   
   std::cout<< a << " * " << b << " = " <<mult ( a, b ) << "\n";
   
   std::cout<< a << " / " << b << " = " << _div ( a, b ) << "\n";
   
   return 0;
   
 }
