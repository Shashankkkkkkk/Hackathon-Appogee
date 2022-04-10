# Hackathon-Appogee


#Importing modules

from chatterbot import ChatBot

from chatterbot.trainers import ListTrainer

from chatterbot.trainers import ChatterBotCorpusTrainer

BankBot = ChatBot(name = 'BankBot',

                  read_only = False,                  

                  logic_adapters = ["chatterbot.logic.BestMatch"],                 

                  storage_adapter = "chatterbot.storage.SQLStorageAdapter")
                  

corpus_trainer = ChatterBotCorpusTrainer(BankBot)

corpus_trainer.train("chatterbot.corpus.english")


greet_conversation = [

    "Hi there!"
  

]


acc_balance_conversation = [

   "What is my account balance"

]


closing_acc_conversation = [

   "Thank You"

]


#Initializing Trainer Object

trainer = ListTrainer(BankBot)


#Training BankBot

trainer.train(greet_conversation)

trainer.train(acc_balance_conversation)

trainer.train(closing_acc_conversation)









