# Backend Setup Guide

## MongoDB Connection Issue Fix

The error "MongoAPIError: URI must include hostname, domain name, and tld" occurs when the MongoDB URI is missing or malformed.

### Steps to Fix:

1. **Create .env file** (if it doesn't exist):
   ```bash
   cp .env.example .env
   ```

2. **Update .env file** with your actual MongoDB URI:
   ```
   MONGO_URI=mongodb://localhost:27017/jobportal
   ```
   
   For MongoDB Atlas:
   ```
   MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/jobportal?retryWrites=true&w=majority
   ```

3. **Valid URI formats**:
   - Local: `mongodb://localhost:27017/database_name`
   - Local with auth: `mongodb://username:password@localhost:27017/database_name`
   - Atlas: `mongodb+srv://username:password@cluster.mongodb.net/database_name`

4. **Restart the server**:
   ```bash
   npm run dev
   ```

### Troubleshooting:
- Ensure MongoDB is running locally if using localhost
- Check your MongoDB Atlas connection string if using cloud
- Verify username and password are correct
- Ensure the database name is included in the URI

### Environment Variables Required:
- `MONGO_URI`: Your MongoDB connection string
- `PORT`: Server port (optional, defaults to 3000)
