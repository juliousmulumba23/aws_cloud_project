# aws_cloud_project
This comprises my simple AWS cloud automation projects.
T h i s   p r o j e c t   c o n t a i n s   a n   A W S   L a m b d a   f u n c t i o n   t h a t   c r e a t e s   a   L i n u x   E C 2   i n s t a n c e   a n d   t e r m i n a t e s   i t   a f t e r   2 0   m i n u t e s .   T h e   L a m b d a   f u n c t i o n   i s   t r i g g e r e d   v i a   a n   H T T P   A P I   c r e a t e d   u s i n g   A P I   G a t e w a y .   T h e   p r o j e c t   i n c l u d e s   a   C l o u d F o r m a t i o n   t e m p l a t e   t o   s e t   u p   t h e   n e c e s s a r y   r e s o u r c e s . 
 
 # #   F e a t u r e s 
 
 -   * * A u t o m a t e d   E C 2   M a n a g e m e n t * * :   A u t o m a t i c a l l y   c r e a t e   a n d   t e r m i n a t e   E C 2   i n s t a n c e s . 
 -   * * H T T P   A P I   I n t e g r a t i o n * * :   T r i g g e r   t h e   L a m b d a   f u n c t i o n   u s i n g   a n   H T T P   A P I . 
 -   * * C o s t   E f f i c i e n c y * * :   C o m p a r e   m u l t i p l e   m o d e l s   t o   o p t i m i z e   c o s t s . 
 -   * * T i m e   S a v i n g s * * :   A u t o m a t e   t e d i o u s   t a s k s   t o   s a v e   d e v e l o p e r   t i m e . 
 
 # #   A r c h i t e c t u r e 
 
 1 .   * * L a m b d a   F u n c t i o n * * :   C r e a t e s   a n   E C 2   i n s t a n c e   a n d   s c h e d u l e s   i t s   t e r m i n a t i o n . 
 2 .   * * A P I   G a t e w a y * * :   P r o v i d e s   a n   H T T P   e n d p o i n t   t o   t r i g g e r   t h e   L a m b d a   f u n c t i o n . 
 3 .   * * C l o u d F o r m a t i o n   T e m p l a t e * * :   S e t s   u p   t h e   L a m b d a   f u n c t i o n ,   A P I   G a t e w a y ,   a n d   n e c e s s a r y   I A M   r o l e s . 
 
 # #   P r e r e q u i s i t e s 
 
 -   A W S   A c c o u n t 
 -   A W S   C L I   c o n f i g u r e d   w i t h   a p p r o p r i a t e   p e r m i s s i o n s 
 -   S 3   b u c k e t   t o   s t o r e   t h e   L a m b d a   f u n c t i o n   c o d e 
 
 # #   S e t u p 
 
 # # #   1 .   U p l o a d   L a m b d a   F u n c t i o n   C o d e   t o   S 3 
 
 1 .   C r e a t e   a   z i p   f i l e   c o n t a i n i n g   y o u r   L a m b d a   f u n c t i o n   c o d e . 
 2 .   U p l o a d   t h e   z i p   f i l e   t o   a n   S 3   b u c k e t . 
 
 # # #   2 .   D e p l o y   C l o u d F o r m a t i o n   S t a c k 
 
 1 .   S a v e   t h e   C l o u d F o r m a t i o n   t e m p l a t e   t o   a   f i l e ,   e . g . ,   	 e m p l a t e . y a m l . 
 2 .   U s e   t h e   A W S   C L I   t o   d e p l o y   t h e   C l o u d F o r m a t i o n   s t a c k : 
 
       ` s h 
       a w s   c l o u d f o r m a t i o n   c r e a t e - s t a c k   - - s t a c k - n a m e   M y L a m b d a H t t p A p i S t a c k   - - t e m p l a t e - b o d y   f i l e : / / t e m p l a t e . y a m l   - - c a p a b i l i t i e s   C A P A B I L I T Y _ N A M E D _ I A M  
 