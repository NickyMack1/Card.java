# Card.java
class Card {
    private String suit;
    private String faceValue;

    public Card(String suit, String faceValue) {
        this.suit = suit;
        this.faceValue = faceValue;
    }

    public String getSuit() {
        return suit;
    }

    public String getFaceValue() {
        return faceValue;
    }

    public String toString() {
        return faceValue + " of " + suit;
    }
}
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class CardDealer {
    public static void main(String[] args) {
        String[] suits = {"Hearts", "Diamonds", "Clubs", "Spades"};
        String[] faceValues = {"Ace", "2", "3", "4", "5", "6", "7", "8", "9", "10", "Jack", "Queen", "King"};

        List<Card> deck = new ArrayList<>();

        // Create a deck of cards
        for (String suit : suits) {
            for (String faceValue : faceValues) {
                Card card = new Card(suit, faceValue);
                deck.add(card);
            }
        }

        // Shuffle the deck
        Collections.shuffle(deck);

        // Deal five random cards
        System.out.println("Dealt cards:");
        for (int i = 0; i < 5; i++) {
            Card dealtCard = deck.get(i);
            System.out.println(dealtCard);
        }
    }
}
