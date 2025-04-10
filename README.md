!pip install thefuzz
!pip install python-Levenshtein
from thefuzz import process  # Import fuzzy matching library

def web3():
    keywords = {
        "who am i": "You are the world’s greatest, having the likes of Nelson Mandela as a neighbour... the special one.",
        "hello": "Hi there!",
        "how are you": "I'm doing well, thanks!",
        "weather": "I'm sorry, I don't know the weather.",
        "goodbye": "Goodbye!",
        "thank you": "You're welcome!",
        "what is your name": "I am a web3 chatbot.",
        "what can you do": "I can answer questions about web3.",
        "what is blockchain": "Blockchain is a decentralized ledger technology that records transactions across multiple computers in a network.",
        "what is nft": "NFT stands for Non-Fungible Token, a unique digital asset that represents ownership of a specific item or piece of content.",
        "what is dao": "DAO stands for Decentralized Autonomous Organization, a form of organization that operates without a central leader or authority.",
        "what is cryptocurrency": "Cryptocurrency is a digital currency that is secured by cryptography.",
        "what is web3": "Web3 is the next generation of the internet, which aims to be decentralized and blockchain-based.",
        "what are the benefits of web3": "Web3 offers several benefits, including increased transparency, security, and control over data.",
        "what are the challenges of web3": "Web3 faces several challenges, including scalability, interoperability, and adoption.",
        "how does web3 work": "Web3 works by using blockchain technology to create a decentralized network of computers that can store and share data.",
        "cryptocurrency": "Digital currency which is secured by cryptography.",
        "blockchain": "A decentralized ledger technology that records transactions across multiple computers in a network.",
        "mining": "The process of generating cryptocurrency by solving complex mathematical problems.",
        "staking": "The process of locking up cryptocurrency in exchange for rewards.",
        "airdrop": "The process of distributing cryptocurrency to users for free.",
        "NFT": "Non-Fungible Token, a unique digital asset that represents ownership of a specific item or piece of content.",
        "DAO": "Decentralized Autonomous Organization, a form of organization that operates without a central leader or authority.",
        "smart contract": "A self-executing contract that is programmed to automatically fulfill its terms when certain conditions are met.",
        "DeFi": "Decentralized Finance, a financial system that operates without intermediaries or centralized authorities.",
        "Web3 Stack": "A set of technologies and protocols that enable the development of decentralized applications and services on the blockchain.",
        "ethereum": "A decentralized platform that enables the creation and deployment of smart contracts and decentralized applications.",
        "bitcoin": "The first cryptocurrency, created in 2009 by Satoshi Nakamoto.",
        "solana": "A blockchain platform that aims to provide fast and scalable transactions.",
        "polygon": "A blockchain platform that aims to provide scalability and interoperability.",
        "avalanche": "A blockchain platform that aims to provide fast and secure transactions.",
        "binance coin": "A cryptocurrency that is used to pay for fees on the Binance blockchain.",
        "litecoin": "A cryptocurrency that is designed to be more environmentally friendly than Bitcoin.",
        "cardano": "A blockchain platform that aims to provide a decentralized and sustainable ecosystem.",
        "tron": "A blockchain platform that aims to provide a decentralized and scalable ecosystem.",
        "stellar": "A blockchain platform that aims to provide fast and secure transactions.",
        "metamask": "A cryptocurrency wallet that allows users to interact with decentralized applications and services on the blockchain.",
        "coinbase": "A cryptocurrency exchange that allows users to buy, sell, and trade cryptocurrency.",
        "binance": "A cryptocurrency exchange that allows users to buy, sell, and trade cryptocurrency.",
        "kraken": "A cryptocurrency exchange that allows users to buy, sell, and trade cryptocurrency.",
        "crypto wallet": "A digital wallet that stores cryptocurrency and allows users to send and receive transactions.",
        "crypto exchange": "A platform that allows users to buy, sell, and trade cryptocurrency.",
        "crypto mining": "The process of generating cryptocurrency by solving complex mathematical problems.",
        "crypto staking": "The process of generating cryptocurrency by solving complex mathematical problems.",
        "crypto staking": "The process of locking up cryptocurrency in exchange for rewards.",
        "crypto lending": "The process of lending cryptocurrency to borrowers in exchange for interest.",
        "borrowing": "The process of borrowing cryptocurrency from lenders in exchange for interest.",
        "crypto derivatives": "Financial instruments that derive their value from the price of an underlying asset, such as cryptocurrency.",
    }

    while True:
        user_input = input("You: ").lower().strip()  # Convert to lowercase and remove extra spaces
        if user_input == "goodbye":
            print("web3: Goodbye!")
            break

        # Use fuzzy matching to find the best match
        best_match, confidence = process.extractOne(user_input, keywords.keys())

        if confidence > 70:  # If match confidence is high enough, return response
            response = keywords[best_match]
        else:
            response = "I don't understand. Can you rephrase?"

        print("web3:", response)

# Run the chatbot
web3()
