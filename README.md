# Ruby on Rails + React (Vite) Setup

## 🛠 Ruby on Rails Installation Steps

### 1. Install RVM  
\curl -sSL https://get.rvm.io | bash -s stable  
source ~/.rvm/scripts/rvm  
rvm -v  
rvm install 3.2.2  

### 2. Install Node  
nvm install {node_version}  

### 3. Install Rails  
gem install rails  

### 4. Create a new Rails project  
rails new my_app  

**Options while creating:**  
- --api : Does not install view folder  
- -d postgresql : Configure with PostgreSQL instead of SQLite  

### 5. To create APIs quickly using scaffold  
rails generate scaffold Post title:string body:text  

In this, “Post” is the name of your route and controller, and `title` and `body` are the fields that will be created in the posts table.

---

## ⚛️ To Connect with Frontend (React)

### 1. Create frontend inside the Rails folder  
npm create vite@latest frontend  

### 2. Add proxy to React server in `frontend/vite.config.js`  
server: {  
  proxy: {  
    '/api': 'http://localhost:3000',  
  },  
}  

### 3. Install foreman gem  
gem install foreman  

### 4. Create `Procfile.dev` in the Rails root and add:  
web: bin/rails server -p 3000  
vite: cd frontend && npm run dev  

### 5. Run the app  
bin/dev  
