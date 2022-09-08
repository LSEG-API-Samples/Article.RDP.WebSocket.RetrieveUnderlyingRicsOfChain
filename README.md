# [Retrieve underlying RICs of chain RIC](https://developers.refinitiv.com/en/article-catalog/article/Retrieve-underlying-RICs-of-chain-RIC)

Working with Refinitiv real-time data, you probably already or is going to come across a specific type of instrument called Chains. The concept of chains is relatively straightforward and decoding them is not that complicated.

## <a id="Introduction"></a>Introduction

Working with Refinitiv real-time data, you probably already or is going to come across a specific type of instrument called Chains. The concept of chains is relatively straightforward and decoding them is not that complicated.

In this article, I'm going to introduce you to a simple and easy way to retrieve the current constituents of a Chain RIC by using an endpoint provided in Refinitiv Data Platform APIs. However, to understand more about a Chain RIC and its structure, we're going to use another way, which is the Refinitiv Real-time market data first. There are many APIs that can be used to retrieve these data, you may check our Real-time API Catalog for more detail. The Refinitiv WebSocket API is used to retrieve the real-time data here as an example of how to retrieve RICs and their data, and then process them.
To find how to form an RDP API call, search for an endpoint in [RDP API Playground](https://apidocs.refinitiv.com/Apps/ApiDocs)

## <a id="Prerequisite"></a>Prerequisite
The code can be run on Jupyter Notebook. To run examples in this article,
-  Access Credentials are required to use RDP API and Websocket. For more detail, please check this page [Refinitiv Data Platform APIs - Quickstart guide](https://developers.refinitiv.com/en/api-catalog/refinitiv-data-platform/refinitiv-data-platform-apis/quick-start).
In this article, the authentication is being done using the token retrived from RDP API that allows you to access content directly within the cloud utilizes the OAuth 2.0 specification to ensure secure communication. While the libraries will shield the user from OAuth token management, the following credentials will be required to access the content:
   - **User ID / Machine ID**	A User ID or Machine ID provided to you - in a Welcome email from Refinitiv
   - **Password**	The User / Machine Password you have set using a link in the above Welcome email
   - **App Key**	An Application Key used to monitor the application. Users can generate/manage their application ID's [here](http://amers1-apps.platform.refinitiv.com/apps/appkeygenerator).

To acquire your Platform credentials, you will need to reach out to your Refinitiv Account Manager.

### Required python libraries and their version:
Python version 3.9.12 is being used here
You may download requirements.txt from this repo then use the command `pip install -r requirements.txt` to install required libraries
-  json==2.0.9
-  requests==2.27.1
-  websocket==1.3.2

## <a id="SourceCodeFiles"></a>Source code files
1. [rdpToken.py](https://github.com/Refinitiv-API-Samples/Article.RDP.WebSocket.RetrieveUnderlyingRicsOfChain/blob/main/rdpToken.py): Utility file to manage access token with RDP API
2. [websocket-underlying-rics-chain.ipynb](https://github.com/Refinitiv-API-Samples/Article.RDP.WebSocket.RetrieveUnderlyingRicsOfChain/blob/main/websocket-underlying-rics-chain.ipynb): Method 1) Get chain constituents with Refinitiv Websocket API
3. [rdp-api-underlying-rics-chain.ipynb](https://github.com/Refinitiv-API-Samples/Article.RDP.WebSocket.RetrieveUnderlyingRicsOfChain/blob/main/rdp-api-underlying-rics-chain.ipynb): Method 2) Get chain constituents with Refinitiv Data Platform API

## <a id="ExampleOutput"></a>Example output
The output is list of Chain constituents (Underlying RICs) printed to Jupyter Notebook console.

## <a id="Conclusion"></a>Conclusion
After finishing reading this article (and maybe some practice with the Python code provided), you should be able to retrieve the Chain constituents list. Two methods of retrieving the data are introduced here, please feel free to pick the one that you're comfortable with. However, you could see that using the RDP API endpoint is much simpler because the endpoint already handles the chain logic for you, unlike the Refinitiv Websocket where you have to handle the message returned from the server by yourself so you need to understand basic chain concept and its structure before working with it.

Then you can use this Chain constituents list to request the data of each constituent itself as a next step.

Last but not least, I hope you have fun with this article and if you have any questions or issues regarding API usage, please don’t hesitate to post your question on our [Q&A forum](https://community.developers.refinitiv.com/)
