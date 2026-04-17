So this is an sample repo, ive done to kickstart my git skills again
https://docs.google.com/document/d/18GuXurK4vvADjwBbhKmz-KOD0eTHVyDUVqgb4eUg9bY/edit?usp=sharing
MONGODB_URI=mongodb+srv://khamesh05_db_user:Kq6cN38RLlwhHwcr@ai-dev.id3kh8c.mongodb.net/genpact-ai-dev?retryWrites=true&w=majority&appName=AI-DEV

node -e "
const mongoose = require('mongoose');
const bcrypt = require('bcryptjs');
require('dotenv').config();

mongoose.connect(process.env.MONGODB_URI).then(async () => {
  console.log('Connected!');
  const User = require('./models/User');
  const users = await User.find({});
  console.log('All users:', users.map(u => ({email: u.email, role: u.role})));
  process.exit();
});
"
