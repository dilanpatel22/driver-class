public class Driverexam 
{
private char[] correctAnswers;
public Driverexam(char[] c)
{
 correctAnswers=c;
}
public int totalCorrect(char[] studentAnswers)
{
 int correct = 0;
 for(int i=0; i<correctAnswers.length; i++)
 {
  if (correctAnswers[i]== studentAnswers[i])
  {
   correct+=1;
  }
  
 }
 return correct;
}
public int totalIncorrect(char[] studentAnswers)
{
 return correctAnswers.length- totalCorrect(studentAnswers);
}
public boolean passed(char[] studentAnswers)
{
 return  (totalCorrect(studentAnswers)/correctAnswers.length>=0.75);
}
public int[] questionsMissed(char[] studentAnswers)
{
 int[] wrong= new int[totalIncorrect(studentAnswers)];
 int index= 0;
 for (int i= 0; i<correctAnswers.length; i++)
  {
  if (correctAnswers[i] != studentAnswers[i])
  {
   wrong[index]= i+1;
   index++;
  }
 }
 return wrong;
}
}
