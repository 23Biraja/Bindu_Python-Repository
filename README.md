# Bindu_Python-Repository
The combined love for Python and JNU brings me here..
here is the code .. for more you can read the attached file..
import nltk
from nltk.stem.lancaster import LancasterStemmer
stemmer=LancasterStemmer()
import string
import numpy as np
import random
import warnings
In [2]:
warnings.filterwarnings('ignore')
#warnings.simplifilter('ignore')

idx=vals.argsort()[0][-2]
 flat= vals.flatten()
 flat.sort()
 req_tfidf = flat[-2]
 if(req_tfidf==0):
 bindu_response=bindu_response+" I am sorry,I am not getting,please do a google 
 return bindu_response 
 else:
 bindu_response = bindu_response+sent_tokens[idx]
 return bindu_response
In [11]:
import nltk.corpus
nltk.download('stopwords', quiet=True, raise_on_error=True)
stop_words = set(nltk.corpus.stopwords.words('english'))
tokenized_stop_words = nltk.word_tokenize(' '.join(nltk.corpus.stopwords.words('eng
class Tokenizer(object):
 def __init__(self):
 nltk.download('punkt', quiet=True, raise_on_error=True)
 self.stemmer = nltk.stem.PorterStemmer()
 
 def _stem(self, token):
 if (token in stop_words):
 return token # Solves error "UserWarning: Your stop_words may be incon
 return self.stemmer.stem(token)
 
 def __call__(self, line):
 tokens = nltk.word_tokenize(line)
 tokens = (self._stem(token) for token in tokens) # Stemming
 return list(tokens)
 
tokenizer = CountVectorizer(min_df=5,
 ngram_range=(1, 2),
 tokenizer=Tokenizer(),
 stop_words=tokenized_stop_words,
lowercase=True)
In [14]:
flag=True
print("BinduBot:Hello!! I'm Bindu,specifically designed to answer some basic querie
while(flag== True):
 user_response = input()
 user_response= user_response.lower()
 if(user_response!='bye'):
 if(user_response=='thanks' or user_response=='thank you'):
 flag= False
 print("BinduBot: you are welcome.. come again for more info")
 else:
 if(greeting(user_response)!= None):
 print("\n BinduBot: "+greeting(user_response)+"\n")
 
 else:
 sent_tokens.append(user_response)
 word_tokens=word_tokens+nltk.word_tokenize(user_response)
 final_words=list(set(word_tokens))
 print("\n BinduBot:",end=" ")
 print("\n ",response(user_response),"\n")
 sent_tokens.remove(user_response)
 
 else:
 flag= False
 print("BinduBot:GoodBye ! Take Care")
8/10/22, 6:54 PM 23_BinduBot
localhost:8888/nbconvert/html/23_BinduBot.ipynb?download=false 4/5
BinduBot:Hello!! I'm Bindu,specifically designed to answer some basic queries abou
t JNU.,if you wanna exit any time,type Bye!
hello
 BinduBot: ask 





 
fellowships
 BinduBot: 
 fellowships/scholarships/ awards:
the details of fellowships/scholarships sponsor by various external agencies/other
departments can be referred to by the interested
candidates by accessing the website of the concerned departments
tudents as per the terms &
conditions of the fellowships and subject to availability of funds, through a sepa
rate circular/notice
for more details , visit the jnu website : https://www.jnu.ac.in . 
thank you
BinduBot: you are welcome.. come again for more inf
