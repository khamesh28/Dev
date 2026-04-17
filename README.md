So this is an sample repo, ive done to kickstart my git skills again
https://docs.google.com/document/d/18GuXurK4vvADjwBbhKmz-KOD0eTHVyDUVqgb4eUg9bY/edit?usp=sharing
MONGODB_URI=mongodb+srv://khamesh05_db_user:Kq6cN38RLlwhHwcr@ai-dev.id3kh8c.mongodb.net/genpact-ai-dev?retryWrites=true&w=majority&appName=AI-DEV

node -e "
const mongoose = require('mongoose');
const bcrypt = require('bcryptjs');
require('dotenv').config();

mongoose.connect(process.env.MONGODB_URI).then(async () => {
  const User = require('./models/User');
  const hash = await bcrypt.hash('admin123', 10);
  const result = await User.updateOne({ email: 'admin@gamil.com' }, { password: hash });
  console.log('Result:', result);
  process.exit();
});
"
