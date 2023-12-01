# TP_Game
Sir Eto na po
  
package game2;
import java.util.Scanner;

interface Player {
    void createCharacter();
    void displayInfo();
}

interface StoryMode {
    void startQuest(String questName, String questDescription) throws InterruptedException;
    void progressStory(String questName) throws InterruptedException;
    void completeQuest(String questName) throws InterruptedException;
}

interface SurvivalMode{
    void faceBoss(String bossName) throws InterruptedException;; 
    void improveCharacter(String questName) throws InterruptedException;;

}

 class Game implements Player, StoryMode, SurvivalMode {
    private String playerName;
    private int health;
    private int level;
    private int armor;
    private int storyProgress;
    public int bossCount;
    public Game() {
        this.health = 100; 
        this.level = 1;   
        this.armor = 0;
        this.storyProgress = 0;
        this.bossCount = 0;
    }

    @Override
    public void createCharacter() {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter your character's name: ");
        playerName = scanner.nextLine();
        System.out.println("Character created!");
    }

    @Override
    public void displayInfo() {
        System.out.println("Player: " + playerName);
        System.out.println("Level: " + level);
        System.out.println("Health: " + health);
    }
 
    public void faceBoss(String bossName) {
        System.out.println("Facing Boss: " + bossName);
        bossCount++;
        if (bossCount < 20) {
            System.out.println("Boss defeated! Choose an upgrade:");
            improveCharacter();
              try {
                Thread.sleep(2000); 
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        } else {
            System.out.println("Congratulations! You've defeated the final boss The Jean Flores Ultimate My Longlasting lonelyFriends of PhilipLagula!");
           
        }
          try {
                Thread.sleep(2000); 
            } catch (InterruptedException e) {
                e.printStackTrace();
    }
    }
   public void improveCharacter() {
        Scanner scanner = new Scanner(System.in);
        System.out.println("1. Increase Health");
        System.out.println("2. Increase Level");
        System.out.println("3. Increase Armor");
        System.out.print("Choose an upgrade (1-3): ");
        int choice = scanner.nextInt();

        switch (choice) {
            case 1:
                health += 82372;
                health++;
                break;
            case 2:
                level+= 210;
                level++;
                break;
            case 3:
                armor +=4332;
                break;
            default:
                System.out.println("Invalid choice. No upgrade selected.");
        }

        displayInfo();
    }
    @Override
    public void startQuest(String questName, String questDescription) throws InterruptedException {
        System.out.println("Started a new quest: " + questName);
        System.out.println("Description: " + questDescription);
        Thread.sleep(2000); 
    }

    @Override
    public void progressStory(String questName) throws InterruptedException {
        System.out.println("Progressing through the story of quest: " + questName);
        storyProgress++;
        Thread.sleep(1500);     }

    @Override
    public void completeQuest(String questName) throws InterruptedException {
        System.out.println("Completed the quest: " + questName + ". Story progress increased.");
        storyProgress += 2;
        Thread.sleep(2000); 
    }
   

    public void anthonyClanIntroduction() throws InterruptedException {
        startQuest("Discover the Anthony Clan", "Uncover the history and traditions of the honorable Anthony Clan.");
        progressStory("Discover the Anthony Clan");
    }

    public void jcClanIntroduction() throws InterruptedException {
        startQuest("Meet the JC Clan", "Learn about the mystical JC Clan and their ancient powers.");
        progressStory("Meet the JC Clan");
    }

    public void familyTragedy() throws InterruptedException {
        startQuest("Family Tragedy", "Witness the devastating invasion that took your family away.");
        progressStory("Family Tragedy");
    }

    public void revengeQuest() throws InterruptedException {
        startQuest("Embark on the Path of Revenge", "Swear an oath to avenge your family and clans from the invaders.");
        progressStory("Embark on the Path of Revenge");
    }

    public void infiltrateEnemyStronghold() throws InterruptedException {
        startQuest("Infiltrate Enemy Stronghold", "Sneak into the enemy's fortress to gather intelligence and seek justice.");
        progressStory("Infiltrate Enemy Stronghold");
    }

    public void confrontInvaders() throws InterruptedException {
        startQuest("Confront the Invaders", "Face the invaders in a fierce battle to reclaim honor and justice.");
        progressStory("Confront the Invaders");
    }

    public void finalShowdown() throws InterruptedException {
        startQuest("Final Showdown", "Prepare for the ultimate confrontation with the leaders of the enemy clans.");
        progressStory("Final Showdown");
        completeQuest("Final Showdown");
    }
     public void Thanks() throws InterruptedException {
     System.out.println("");
            System.out.println("");
            System.out.println("");
            System.out.println("");
            System.out.println("");
            System.out.println("thanks to Ampogi ni sir JC sana gawin niyang 100 ito, thanks to Ampogi ni sir JC sana gawin niyang 100 ito ,thanks to Ampogi ni sir JC sana gawin niyang 100 ito ,thanks to Ampogi ni sir JC sana gawin niyang 100 ito ");
            System.out.println("Thanks to lakas amats mo Anthony At Philip");
            System.out.println("Napakapogi ko");
            System.out.println("Bakit mo binasa ito");
            System.out.println("hala hanggang dito binabasa niya pa din");
            System.out.println("Antibay oh bwuahahaah");
            System.out.println("De joke");
            System.out.println("eto na discription for my EsonTheRevenge");
            System.out.println("Dear Player ");
            System.out.println("On behalf of my half in EsonTheRevenge, I want to extend my heartfelt ");
            System.out.println("for choosing to embark on this adventure with me yiee ");
            System.out.println("Your presence in my game has added a special spark to the virtual world I crafted.");
            System.out.println("Thank you once again for being an integral part of my gaming community.");
            System.out.println("ay your adventures in  continue to be filled with excitement, discovery, and triumph!");
            System.out.println("");
            System.out.println("");
            System.out.println("");
            System.out.println("");
            System.out.println("Best regards,");
            System.out.println("");
            System.out.println("");
            System.out.println("");
            System.out.println("");
            System.out.println("EsonTheRevenge");
     }

    @Override
    public void improveCharacter(String questName) throws InterruptedException {
     
    }
}
public class Main {
    public static void main(String[] args) {
        Game game = new Game();
        game.createCharacter();
        

        Scanner scanner = new Scanner(System.in);
        System.out.println("Choose a mode: ");
        System.out.println("1. Survival Mode");
        System.out.println("2. Story Mode");
        int choice = scanner.nextInt();
              
          

        if (choice == 1) {
           
            while (game.bossCount < 20) {
                game.faceBoss("Boss " + (game.bossCount + 1));
            }
        } else if (choice == 2) {
        
            try {
                game.anthonyClanIntroduction();
                game.jcClanIntroduction();
                game.familyTragedy();
                game.revengeQuest();
                game.infiltrateEnemyStronghold();
                game.confrontInvaders();
                game.finalShowdown();
                game.Thanks();
          
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        } else {
            System.out.println("Invalid choice. Exiting.");
        }

    }
}
