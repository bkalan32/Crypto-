'''
# KryptoJobs2Go - README

## Background
KryptoJobs2Go is a disruptive application developed by our startup. It allows customers to find fintech professionals, hire them, and pay them using cryptocurrency. As the lead developer, your task is to integrate the Ethereum blockchain network into the application, enabling instant cryptocurrency payments to the hired professionals.

## What You're Creating
In this project, you will work on the `fintech_finder.py` file, which contains the code for the web interface of KryptoJobs2Go. You will import Ethereum transaction functions from the `crypto_wallet.py` script and integrate them into the application. Additionally, you will write code to sign and run payment transactions, and inspect the transactions in Ganache.

## Files
Download the following files to get started:
- `Module 19 Challenge files` (link provided)

## Instructions

### Step 1: Import Ethereum Transaction Functions into the KryptoJobs2Go Application
1. Review the code in the `crypto_wallet.py` file, which contains the Ethereum transaction functions.
2. Add your mnemonic seed phrase provided by Ganache to the `SAMPLE.env` file and rename it to `.env`.
3. Open the `fintech_finder.py` file and import the following functions from `crypto_wallet.py`:
   - `generate_account`
   - `get_balance`
   - `send_transaction`
4. In the Streamlit sidebar section of the code, create a variable named `account` and set it equal to a call to the `generate_account` function. This will create the hierarchical deterministic (HD) wallet and Ethereum account for the KryptoJobs2Go customer.
5. Define a new `st.sidebar.write` function to display the balance of the customer account. Call the `get_balance` function inside this function and pass it `account.address` as the parameter.

### Step 2: Sign and Run a Payment Transaction
1. Calculate the wage, in ether, for a fintech professional based on their hourly rate and the number of hours they worked. Retrieve the hourly rate from the `candidate_database` using `candidate_database[person][3]` and multiply it by the hours variable. Save the result in a variable named `wage`.
2. Write the value of `wage` to the Streamlit sidebar using `st.sidebar.write`.
3. Implement code to allow a customer (you) to send an Ethereum blockchain transaction that pays the hired candidate. Inside the `if st.sidebar.button("Send Transaction")` block, call the `send_transaction` function and pass it the following parameters:
   - Your Ethereum account information (accessed via the `account` variable).
   - The `candidate_address` value (created when a candidate is selected).
   - The `wage` value, which should be passed to the `toWei` function to determine the payment value in wei.
4. Save the transaction hash returned by the `send_transaction` function in a variable named `transaction_hash` and display it in the web interface.

### Step 3: Inspect the Transaction in Ganache
1. Navigate to the project folder containing the `.env`, `fintech_finder.py`, and `crypto_wallet.py` files in your terminal. Activate your Conda dev environment if it's not already active.
2. Launch the Streamlit application by running `streamlit run fintech_finder.py` in the terminal.
3. On the web page that opens, select a candidate from the drop-down menu and enter the number of hours you want to hire them for.
4. Click the "Send Transaction" button to sign and send the transaction using your Ethereum account information.
5. Open Ganache and go to the Transactions section.
6. Take a screenshot of your address balance and history in Ganache and save it in the README.md file.
7. Take a screenshot of the transaction details in Ganache and save it in the README.md file.
8. Click on the recipient's address in the transaction details to view their balance and history in Ganache.
9. Take a screenshot of the recipient's address balance and history in Ganache and save it in the README.md file.
