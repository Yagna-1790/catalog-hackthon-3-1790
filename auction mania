import time

class Auction:
    def __init__(self, item_name, starting_price):
        self.item_name = item_name
        self.current_price = starting_price
        self.highest_bidder = None
        self.bids = []

    def place_bid(self, bidder_name, bid_amount):
        if bid_amount > self.current_price:
            self.current_price = bid_amount
            self.highest_bidder = bidder_name
            self.bids.append((bidder_name, bid_amount))
            print(f"New highest bid by {bidder_name}: ${bid_amount}")
        else:
            print("Bid too low. Please place a higher bid.")

    def show_current_bid(self):
        if self.highest_bidder:
            print(f"Current highest bid: ${self.current_price} by {self.highest_bidder}")
        else:
            print(f"No bids yet. Starting price: ${self.current_price}")

    def auction_summary(self):
        print("\nAuction Summary")
        print(f"Item: {self.item_name}")
        print(f"Winning bid: ${self.current_price} by {self.highest_bidder}")
        print("Bid history:")
        for bidder, bid in self.bids:
            print(f" - {bidder} bid ${bid}")

def main():
    print("Welcome to the Auction Mania !")
    print("here this is a custmoised auction mania where select your product and auction it accordingly ")

    item_name = input("Enter the name of the item for auction: ")
    starting_price = float(input("Enter the starting price for the item: "))

    auction = Auction(item_name, starting_price)

    auction_duration = 60  # Auction lasts 60 seconds
    start_time = time.time()

    while time.time() - start_time < auction_duration:
        print("\nCurrent Status:")
        auction.show_current_bid()

        bidder_name = input("Enter your name: ")
        bid_amount = float(input(f"Enter your bid for {item_name}: $"))

        auction.place_bid(bidder_name, bid_amount)

        time_remaining = int(auction_duration - (time.time() - start_time))
        print(f"Time remaining: {time_remaining} seconds\n")
        time.sleep(2)  # Short delay for demonstration purposes

    print("\nAuction ended!")
    auction.auction_summary()

if __name__ == "__main__":
    main()
