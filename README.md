# CSCI2720 Project (21-22 T2) - Weathering with Me

## Programming Languages and relevant tools

- React JS
- Node JS
- MongoDB
- HTML
- CSS
- Postman (for testing HTTP)
- MongoDB Compass (for checking the database)

## Group Members

Alvin CHAN,
Chun Yeung CHOW,
Ngou Shan WONG,
Siu Fung CHEUNG,
Wing Lam CHENG,
Yee Han CHENG

## Instructions
To open this web app, do the following steps: 

Step 1: Pull ALL files  
Step 2: Go to frontend and backend respectively and execute `npm install` respectively (just in case)  
Step 3: Execute `npm run build` in frontend  
Step 4: Execute `npm start` in backend  
Step 5: Go to `localhost:4000` and check!  


# Deploy in AWS instance with port 80

Step 1: Have your AWS instance

Step 2: Git clone the project

Step 3: install pm2 package globally

        npm install pm2 -g
        
Step 4: Redirect port 80 to port 3000 command because there is admin permission denied for using port under 1000 (reference link: https://stackoverflow.com/questions/16573668/best-practices-when-running-node-js-with-port-80-ubuntu-linode)

        sudo iptables -t nat -A PREROUTING -i eth0 -p tcp --dport 80 -j REDIRECT --to-port 3000
        
        
Step 5: in Frontend folder run pm2 command 

        pm2 start npm -- start
        
Step 6: Backend same as Frontend

        pm2 start server.js

Everything is ok now! check with your public IP address.


CSCI2720 - Project Outline
Group Members (SID):
Alvin CHAN (1155108897)
Cheng Yee Han (1155143426)
Wong Ngou Shan (1155141835)
Cheng Wing Lam (1155125313)
Chow Chun Yeung (1155131406)
Cheung Siu Fung (1155110966)
Data Source:
Option 1: Regional Weather in Hong Kong
Data Source Link:
https://data.gov.hk/en-data/dataset/hk-hko-rss-latest-one-minute-mean-air-temp
https://data.gov.hk/en-data/dataset/hk-hko-rss-latest-one-minute-mean-rh
https://data.gov.hk/en-data/dataset/hk-hko-rss-latest-ten-minute-wind-info
Our Planned Data Schema:
User:
- Username (unique + required) - String of 4~20 chars
- Pwd (required) - String of 4~20 chars, hashed
- Admin (required) - Boolean
- Favourite (array of location._id) - Array
Location:
- Location Name (unique + required) - String
- Location lat (unique + required) - String
- Location long (unique + required) - String
- User Comment (array of {User._id, comment: string}) - Array
APIs to be used:
- data.gov.hk (as per requirement)
- Google Maps
Platforms to be used:
For our frontend framework, we will be adopting ReactJS to develop our User Interface. Our
main reason for choosing ReactJS is because we believe that we can implement SPA easily
with ReactJS. Furthermore, we might also include Bootstrap library for stylistic purposes.
As for our backend framework, per requirement, we will be using NodeJS as the backbone of
our server. However, for our Database, we will be using MongoDB as our database due to the
fact that we are more familiar at implementing noSQL into our server than MySQL and other
relational database.



## P.S 

All data is grabbed from https://www.weatherapi.com/

You need to create an account to get the API key from that.

## Screenshots
<img width="1399" alt="Screenshot 2023-07-18 at 12 55 21" src="https://github.com/Vincy-Cheng/CSCI2720-Project/assets/60846680/5b3f2c21-4d4b-4b6a-b643-0eada146470b">
