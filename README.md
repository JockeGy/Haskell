module Blackjack where
import Cards
import Wrapper
import System.Random

-- An empty hand
tomhand = Empty

-- The value of a hand
valueRank :: Rank -> Integer
valueRank (Numeric n) = n
valueRank Jack = 10
valueRank Queen = 10
valueRank King = 10
valueRank Ace = 11

valueCard :: Card -> Integer
valueCard (Card rank _) = valueRank rank

numberOfAces :: Hand -> Integer
numberOfAces Empty = 0
numberOfAces (Some (Card Ace _) hand) = 1 + numberOfAces (hand)
numberOfAces (Some (Card any _) hand) = 0 + numberOfAces (hand)


-- Card = Card Rank Suit
-- Card = Card (Numeric 5 Hearts)
	
	

--gameOver:: Hand --> Bool


--winner:: Hand -> Hand -> Player

--fullDeck:: Hand

--draw:: Hand -> Hand -> (Hand, Hand) -- Use the syntax (a,b) to return
	--if deck == empty, error"draw; The deck is empty."

-- COMMENT Given the deck left after Guest, let the bank play:
--playBank:: Hand -> Hand
-- COMMENT To draw a card from the deck you can use "where" in the following way:
--playBank' deck bankHand ...
			-- ...
	--where (deck', bankHand') = draw deck bankHand -- read about "where" in the book

-- COMMENT Given a hand of cards, shuffle them
-- shuffle:: StdGen -> Hand -> Hand

