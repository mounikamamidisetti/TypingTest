import java.util.Scanner;

public class TypingTest {
	public static void accuracy(String sentence, String my_sentence) {
		double chars=0;
		double total_char=sentence.length();
		for(int i=0;i<sentence.length();i++) {
			if(sentence.charAt(i)==my_sentence.charAt(i)) {
				chars++;
			}
		}
		double percentage=(chars/total_char)*100;
		System.out.println("Your total accuracy is  "+percentage);
	}

	public static void main(String[] args) {
		Scanner input=new Scanner(System.in);
		System.out.println("enter the sentence");
		String sentence=input.nextLine();
//		String sentence="hello everyone welcome to the world";
		System.out.println("Welcome to typing application ");
		System.out.println("Write the following sentence \n"+sentence+"\n");
//		Scanner input=new Scanner(System.in);
		long start_time=System.currentTimeMillis();
		String my_sentence=input.nextLine();
		long end_time=System.currentTimeMillis();
		long total_time=end_time-start_time;
		double seconds=total_time/1000;
		double words=sentence.split(" ").length;
		double wpm=(words/seconds)*60;
		System.out.println("Your total words per minute "+wpm);
		System.out.println("Your total time :"+seconds+" Seconds");
		if(sentence.equals(my_sentence)) {
			System.out.println(" WOW Your accuracy is 100% ");
		}else  accuracy(sentence, my_sentence);
		
		
	}

}
