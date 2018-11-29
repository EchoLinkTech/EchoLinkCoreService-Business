# Bulk-upload
Dapp to upload user's credential data(csv and images) to EKO-Pops

## Prerequisites

- Private account:
You should have a private account with mnemonic key or priv_key to start a transaction.

- Mnemonic key
After click on metamask logo, you will be provided with an option to `Create a new vault`. Enter a strong password and click `OK`. Metamask will now show you your seed(mnemonic key). It is very important that you copy and store those 12 words, without them you cannot restore your wallet. 

## Steps to run bulk-upload on local system

- Clone the repo `EchoLinkPrivateService`

- Go to credentials-bulk-upload module and run `npm install`

- Start the server: 
`node app-server`

- UI can be accessed on `localhost:8000`.
- Server is deployed and can be accessed on [http://18.216.156.198:8000/](http://18.216.156.198:8000/)

It displays two sections- one to upload csv file and other to upload images.

- In first section, `.csv file < 50 entries` containing fields
``` 
    issuer      |     recipient     |     status      |   image file name |
```
  eg:   
```    
    TechRacers  |      EchoLink      |     Success     |      image.png   |    
```
can be uploaded. The imageName field name must match with the uploaded images name.

- In second section, images can be uploaded with .png |.jpg |.jpeg format and  with `file size < 500kb`. The images name should match with the entries in csv file uploaded.

- After successful upload of csv and image files, we can see a preview of images uploaded with the corresponsing csv data containing issuer, recipient and status.

- A user can remove the images and upload them again if he wants.

- On clicking the `Upload` button in the bottom, a dialog will appear.
- We are provided with two options -
    - Enter mnemonic
    - Enter Private Key

- After verification of menmonic/private key, a transaction will happen which will save images to IPFS and credential data to EKO-Pops node.