# Firebase Indexes Setup Guide

This document explains how to set up the required composite indexes for the application to work properly. Firestore requires indexes for certain types of queries, especially those that filter by a field and sort by another field.

## Required Indexes

### 1. Materials Index

Create an index for the `materials` collection to query by `trainerId` and sort by `uploadedAt`:

👉 [Click here to create the Materials index](https://console.firebase.google.com/v1/r/project/hackathon-fa617/firestore/indexes?create_composite=ClFwcm9qZWN0cy9oYWNrYXRob24tZmE2MTcvZGF0YWJhc2VzLyhkZWZhdWx0KS9jb2xsZWN0aW9uR3JvdXBzL21hdGVyaWFscy9pbmRleGVzL18QARoNCgl0cmFpbmVySWQQARoOCgp1cGxvYWRlZEF0EAIaDAoIX19uYW1lX18QAg)

### 2. Resumes Index

Create an index for the `resumes` collection to query by `studentId` and sort by `uploadedAt`:

👉 [Click here to create the Resumes index](https://console.firebase.google.com/v1/r/project/hackathon-fa617/firestore/indexes?create_composite=Ck9wcm9qZWN0cy9oYWNrYXRob24tZmE2MTcvZGF0YWJhc2VzLyhkZWZhdWx0KS9jb2xsZWN0aW9uR3JvdXBzL3Jlc3VtZXMvaW5kZXhlcy9fEAEaDQoJc3R1ZGVudElkEAEaDgoKdXBsb2FkZWRBdBACGgwKCF9fbmFtZV9fEAI)

### 3. Notifications Index

Create an index for the `notifications` collection to query by `userId` and sort by `createdAt`:

👉 [Click here to create the Notifications index](https://console.firebase.google.com/v1/r/project/hackathon-fa617/firestore/indexes?create_composite=ClVwcm9qZWN0cy9oYWNrYXRob24tZmE2MTcvZGF0YWJhc2VzLyhkZWZhdWx0KS9jb2xsZWN0aW9uR3JvdXBzL25vdGlmaWNhdGlvbnMvaW5kZXhlcy9fEAEaCgoGdXNlcklkEAEaDQoJY3JlYXRlZEF0EAIaDAoIX19uYW1lX18QAg)

## How to Create Indexes

1. Click on the links above to go directly to the index creation page
2. Sign in to your Firebase console if prompted
3. Review the index settings (they should be pre-filled from the link)
4. Click "Create index" button
5. Wait for the index to be created (it may take a few minutes)
6. Refresh your app after all indexes are created

## Manual Creation (Alternative Method)

If the links don't work, you can manually create the indexes:

1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Select your project
3. Go to Firestore Database → Indexes tab
4. Click "Add index"
5. Fill in the details for each index:

### Materials Index
- Collection: materials
- Fields:
  - trainerId (Ascending)
  - uploadedAt (Descending)
- Query scope: Collection

### Resumes Index
- Collection: resumes
- Fields:
  - studentId (Ascending)
  - uploadedAt (Descending)
- Query scope: Collection

### Notifications Index
- Collection: notifications
- Fields:
  - userId (Ascending)
  - createdAt (Descending)
- Query scope: Collection

## CORS Issues with Firebase Storage

If you're experiencing CORS issues with Firebase Storage (errors when uploading files), you may need to configure CORS for your Firebase project:

1. Install the Firebase CLI: `npm install -g firebase-tools`
2. Login to Firebase: `firebase login`
3. Initialize your project: `firebase init storage`
4. Create a file named `cors.json` with the following content:
   ```json
   [
     {
       "origin": ["*"],
       "method": ["GET", "POST", "PUT", "DELETE"],
       "maxAgeSeconds": 3600
     }
   ]
   ```
5. Set CORS configuration: `gsutil cors set cors.json gs://your-storage-bucket-name`

For a more secure configuration, replace `"*"` with your specific domain. 