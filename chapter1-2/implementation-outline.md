# implementation outline

I would divide this work into four parts

Part 1 - Frontend Work
- Add a button to pin the message while hovering on the particular message and the experience should be smooth with some effects and chat section file is located at the /src/components/discussion/chat.tsx.
- On Clicking the button it will fire the endpoint POST "/chat/:id/pin" and handle all success and failure scenario.
- On Top in Chat Section there is highlighted Pinned Message Section. Implement Design of Pinned Message Section according to figma and check all aligning, margins, paddings, format etc aligns with the project.
- After Design Implementation implement Api to retrieve pinned message from endpoint GET "chat/pinned-message". 
- Now you can see the pinned message, by default the active time of pinned message is 10 min you have to provide option to edit active time of pinned message. First Implement Design according to figma to edit active time line.
- After implementing the design integrate the API to edit active time of pinned message having endpoint PUT "chat/pinned-message/:id/active-time?time=50min" 
- Show the live remaining active time of pinned-message and when it comes to end it indicates in red animated color.
- Ensure responsiveness and structure of Application.

Part 2 - Backend Work
- Create Table named "pinned-messages" for storing pinned messages in active discussion 
- Add a Post Request with endpoint "/chat/:id/pin" in file located at "/app/feature/chat/chat-controller.ts" that accept chatId as parameter and it will store message in pinned messages table with default 10 min active period 
- Add a Get Request with endpoint "/chat/pinned-message" in file located at "/app/feature/chat/chat-controller.ts" it will return  pinned messages of discussion. 
- Add a Put Request with endpoint "chat/pinned-message/:id/active-time" in file located at "/app/feature/chat/chat-controller.ts" that accept pinned message id as parameter and time as query params and it will update the active time of pinned message. 
- Ensure to follow the coding structure.  

Part 3 - Sample Test Cases
- In the Active Discussion Mark any chat as pinned message and verify the entries are stored in tables
- Ensure all Pinned Message shows correctly.
- Design and All the Effects are Working or not.
- Ensure you are able to change active time of pinned message 

Part 4 - Integration work and Verifications
- Verify the work of frontend and backend are properly aligned. 
- Frontend Api Calls are directed to Right path.
- Verify Sample Test Cases Provided for verification to ensure the feature working.
- Generate Sample Test Cases of the feature and test them for better quality.