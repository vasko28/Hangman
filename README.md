import java.util.ArrayList;
import java.io.*;
import java.util.Scanner;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

public class Hangman {
public static void main(String[] args) {
    HashMap<String, ArrayList<String>> Data = new HashMap<String, ArrayList<String>>();
    ArrayList<String> _FootballTeams = new ArrayList<String>();
     _Footballteams.add("Manchester United");
     _Footballteams.add("Arsenal");
     _Footballteams.add("Chelsea");
     _Footballteams.add("Liverpool");
     _Footballteams.add("FC Bayern München");
     _Footballteams.add("Juventus");
     _Footballteams.add("Real Madrid");
     _Footballteams.add("FC Barcelona");
     _Footballteams.add("Olympique de Marseille");
     _Footballteams.add("Paris Saint-Germain");
    ArrayList<String> _Books = new ArrayList<String>();
    _Books.add("In Search of Lost Time");
    _Books.add("Don Quixote");
    _Books.add("Ulysses");
    _Books.add("The Great Gatsby");
    _Books.add("Moby Dick");
    _Books.add("Hamlet");
    _Books.add("War and Peace");
    _Books.add("The Odyssey");
    ArrayList<String> _Programmingprinciples = new ArrayList<String>();
    _Programmingprinciples.add("Encapsulation");
    _Programmingprinciples.add("Abstraction");
    _Programmingprinciples.add("Inheritance");
    _Programmingprinciples.add("Polymorphism");
    _Programmingprinciples.add("KISS");
    _Programmingprinciples.add("DRY");
    _Programmingprinciples.add("Open Closed");
    _Programmingprinciples.add("Single Responsibility");
    _Programmingprinciples.add("Composition over inheritance");

    Data.put("A", _FootballTeams);
    Data.put("B", _Books);
    Data.put("C", _Programmingprinciples);

    public class fileStream {
         try {

         OutputStream os = new FileOutputStream("Hangman.txt");
         for(int x = 0; x <= Data.length ; x++) {
            os.write( _Data[x] );
         }
         os.close();
      } catch (IOException e) {
         System.out.print("Exception");
      }
   }
}

Scanner reader = new Scanner(System.in);
System.out.printIn("Please choose a category:" +'\n + "Football Teams" +'\n'+ "Books" +'\n'+ "Programming Principles");
reader.close();

public HashMap<String, List<String>> read() {
        HashMap<String, List<String>> Data = new HashMap<>();
        File file = new File(PATH);
        try (BufferedReader br = new BufferedReader(new FileReader(file))) {
            for (String line; (line = br.readLine()) != null; ) {
                Matcher matcher = PATTERN.matcher(line);
                while (matcher.find()) {
                    List<String> values = Arrays.stream(matcher.group(2).split(",")).map(String::trim).collect(Collectors.toList());
                    data.put(matcher.group(1),values);
                }
            }
        }catch (IOException e) {
          System.out.print("Exception");
        }
    }
}

String phrase = Data[(int) (Math.random() * Data.length)];
phrase = phrase.replaceAll(" ", "  ");                                                                                      
String phrase1 = phrase.replaceAll("[A-Z]", "_");
int attempts = 10;
int score = 0;

      while (attempts <= 10) {
      System.out.println("Attempts left:" + attempts);
      System.out.println("Current phrase:" + phrase1);
      System.out.println("Please enter a letter:");
      char letter = input.nextLine();
             if (phrase.charAt(i) != letter) {
                System.out.println("The phrase doesn't have this letter.);
                attempts--;
                System.out.println("Attempts left:" + attempts);
                System.out.println("Current phrase:" + phrase1);
                System.out.println("Please enter a letter:");
                char letter = input.nextLine();
           } else if (phrase.charAt(i) == letter) {
                String phrase2;
	        phrase2 = phrase1.substring(0, position) + letter + phrase1.substring(position + 1);
	        phrase2 = phrase2.replaceAll("_", "_ ");
                phrase1 = phrase2;
                System.out.println("Attempts left:" + attempts);
                System.out.println("Current phrase:" + phrase1);
                System.out.println("Please enter a letter:");
                char letter = input.nextLine();
           } if attempts == 10 {
                System.out.printIn("Game Over");
           } else if (phrase == phrase1) {
                System.out.printIn("Congratulations you have revealed the phrase:");
                System.out.printIn(phrase1);
                score++;
                System.out.printIn("Current score:" +score);
           }
             
       }
   }
}
