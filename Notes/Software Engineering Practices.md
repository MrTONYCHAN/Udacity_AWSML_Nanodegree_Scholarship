# Clean and Modular Code

Production code: Software running on production servers to handle live users and data of the intended audience. Note that this is different from production-quality code, which describes code that meets expectations for production in reliability, efficiency, and other aspects. Ideally, all code in production meets these expectations, but this is not always the case.
---------------
Clean code: Code that is readable, simple, and concise. Clean production-quality code is crucial for collaboration and maintainability in software development.
-------------------
Modular code: Code that is logically broken up into functions and modules. Modular production-quality code that makes your code more organized, efficient, and reusable.
----------------------
Module: A file. Modules allow code to be reused by encapsulating them into files that can be imported into other files
-----------------------------

# Refactoring Code

Refactoring: Restructuring your code to improve its internal structure without changing its external functionality. This gives you a chance to clean and modularize your program after you've got it working.
---------------
Since it isn't easy to write your best code while you're still trying to just get it working, allocating time to do this is essential to producing high-quality code. Despite the initial time and effort required, this really pays off by speeding up your development time in the long run.
---------------------------
You become a much stronger programmer when you're constantly looking to improve your code. The more you refactor, the easier it will be to structure and write good code the first time.
---------------------------------

Quiz: Buying stocks
===================
Imagine you analyzed several stocks and calculated the ideal price, or limit price, at which you'd want to buy each stock. You write a program to iterate through your stocks and buy it if the current price is below or equal to the limit price you computed. Otherwise, you put it on a watchlist. Below are three ways of writing this code. Which of the following is the most clean?

# Choice A
stock_limit_prices = {'LUX': 62.48, 'AAPL': 127.67, 'NVDA': 161.24}
for stock_ticker, stock_limit_price in buy_prices.items():
    if stock_limit_price <= get_current_stock_price(ticker):
        buy_stock(ticker)
    else:
        watchlist_stock(ticker)
# Choice B
prices = {'LUX': 62.48, 'AAPL': 127.67, 'NVDA': 161.24}
for ticker, price in prices.items():
    if price <= current_price(ticker):
        buy(ticker)
    else:
        watchlist(ticker)
# Choice C
limit_prices = {'LUX': 62.48, 'AAPL': 127.67, 'NVDA': 161.24}
for ticker, limit in limit_prices.items():
    if limit <= get_current_price(ticker):
        buy(ticker)
    else:
        watchlist(ticker)
        
 # Which code is most clean
 ## Choice C
 Choice C was the most simple while also being descriptive. Choice A unnecessarily included the word stock everywhere, when we can already assume we are dealing with stocks based on the context. Naming everything with this can be redundant unless there is a clear reason to differentiate it with something similar. Choice B was also passable but could have more clearly differentiated the limit prices from the current price.
 
 
