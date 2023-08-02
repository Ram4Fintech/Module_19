# Module_19# Module-19-Final: Cryptocurrency Wallet


## Objective

My aim here is to integrate the Ethereum blockchain network into the application in order to enable customers to instantly pay the fintech professionals with cryptocurrency Ethereum.

## The method

Two files have been used to achieve this objective -  `krypto_jobs.py` and `crypto_wallet.py`. The first file `krypto_jobs.py contains the web interface using the Streamlit library. 

The second file `crypto_wallet.py` contains the Ethereum transaction functions that are imported into the first file `krypto_jobs.py`
The results of this challenge are then outputted through KryptoJobs2Go interface program that is in the `krypto_jobs.py` file.

By integrating these two files we are able to automate the process in generating a digital wallet, thereby accessing Ethereum account balances, and signing and sending transactions via a personal Ethereum blockchain called Ganache.

The steps to achieve this objective are listed below:

## Step 1: Import Ethereum Transaction Functions into the KryptoJobs2Go Application

The stratup codes in crypty_wallet.py contains Ethereum transactions functions such as wallet, wallet.derive_acount, get_balance, fromWei, estimateGas, sendRawTransaction, and others, to enable automating the processes of these functions

I imported the relevant transaction functions (geenerate_account, get_balance, and send_transaction) from the `crypto_wallet.py` script into the file `krypto_jobs.py`, the latter file containing the customer interface codes. The goal is to  enable customer interface for an assumed customer KryptoJobs2Go

 As per the instructions, I got the  mnemonic seed phrases from  Ganache to the starter code’s `SAMPLE.env` file. After doing this, I renamed the file `.env`.

 Using the Streamlit sidebar section of code, a variable called 'account' was created and this was made equal to the `generate_account` function, which in turn helped to create the wallet and Ethereum account for the 
 customer KryptoJobs2Go.
 In the same way, I used the  `st.sidebar.write` function to display the balance of the customer’s account and also  called the `get_balance` function to get the balance in the Ethereum account and pass it your Ethereum `account.address`.

## Step 2: Sign and Execute a Payment Transaction

I wrote the equation to calculate the candidates's wage using the hourly rate provided in the candidate database and by multiplying this by the number of hours worked. Then by using the st.sidebar.write function I wrote the wages to the Streamlit sidebar

The next step was to call the send_transaction function "if st.sidebar.button"("Send Transaction") and save it as a variable called transaction_hash. This is to enable sending the wage to the correct account (address) of a chosen candidate. To complete the if statement, the following parameters were added within: the account, candidate_addrress and the wage and have it displayed on the application’s web interface, using the st.sidebare.write function

## Step 3: Inspect the Transaction

Finally it was time to test the KryptoJobs2Go application with the integrated Ethereum wallet and see how the results show up on Ganache. I took the following steps

1. in my  terminal, I traced the path to the project folder that contains your `.env` file and the `krypto_jobs.py` and `crypto_wallet.py` files. Prior to this step, I ensured that the conda 'dev' environment was activated

2. After tracing the path I ran the code `streamlit run krypto_jobs.py`.

3. Thereafter on the following page I selected a candidate (Jo) and gave her 208 hours to be paid. The interface then calculated the total ETH for wages and let me click the button for Send Transaction. Here is the image for this: ![Candidate and hours selection Jo ](https://github.com/Ram4Fintech/Homework-Week-19/assets/121836558/64ae2f54-2d80-4da3-a3cb-ebfc85dc6147). However this resulted in an error message as shown in this image:
![Error message after Send Transaction part 1](https://github.com/Ram4Fintech/Homework-Week-19/assets/121836558/fc69ef3f-bf06-4803-9b75-b99ac5b260c6)
I could not understand what this error meant, in terms of gas price and what I should do to rectify. I consulted my class tutors during office hours and they fould out that similar issues were being faced by other students too. The issue is that in the crypto_wallet.py file, the variable "gasPrice' was set to 0(zero) in Line 73, which was imported into the krypto_jobs.py file and this was supposedly incorrect, the correct amount for "gasPrice" should have been 20000000000. Once I corrected this error in that file and ran the streamlit code again, it worked well and I could get the results for the employee Lane first to test (1 ETH) and the results are here:
![Successful Send Transaction validated no 1](https://github.com/Ram4Fintech/Homework-Week-19/assets/121836558/bec0f359-5781-4764-b721-43c0ce1bf4f4)
I then tested sending the original wage transaction for employee Jo with 208 ETH and the successful results are shown here:
![Successful Send Transaction validated no 2](https://github.com/Ram4Fintech/Homework-Week-19/assets/121836558/148d51ae-5e1a-4894-9f4d-14dbeed3441d)

To close off, I ensured that the 2 send transactions as above are correctly reflected in Ganache blockchain and this is confirmed in the following image:
![Screenshot of transactions in Ganache](https://github.com/Ram4Fintech/Homework-Week-19/assets/121836558/77c5d353-a32a-4851-91c3-546351e25c42)
In addition I also ensured that the balance in the Ethereum account reflects the correct amount after these two transactions and this is shown in this final image:
![Screenshot of account balance in Ganache](https://github.com/Ram4Fintech/Homework-Week-19/assets/121836558/c0ed26ff-d1ae-4927-b411-9b2450e6a2c9)





