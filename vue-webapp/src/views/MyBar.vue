<template>
    <nav class="navbar"> 
        <div class="wrapper"> 
            <div class="logo">
                <router-link to="/">
                    <img src="@/assets/logo.png" alt="Logo" />
                </router-link>
            </div>
            <div>
        <ul class="nav-links">
          <label f="close-btn" class="btn close-btn"></label>
            <li> <router-link to="/">Home</router-link></li>
            <li> <router-link to="/products">MyCard</router-link></li>
            <li><router-link to="/about">About</router-link></li>
        </ul>
    </div>
        </div>
    </nav>

    
</template>
<script>
import logo from "@/assets/logo.png";
export default {
    name: "MyBar",
    data (){
        return {
              logo,
        }   
    },
};
</script>

<style scoped>
/* Navbar หลัก */
.navbar {
  background: linear-gradient(90deg, #CC0000, #CC0033); /* ไล่เฉดสีแนวกีฬา */
  padding: 15px 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  position: sticky;
  top: 0;
  z-index: 1000;
  font-family: 'Arial', sans-serif;
  border-bottom: 3px solid #ff4500; /* เพิ่มเส้นขอบด้านล่าง */
}

/* โลโก้ */
.logo img {
  height: 60px; /* ขนาดโลโก้ */
  width: auto;
  cursor: pointer;
  transition: transform 0.3s ease;
}

.logo img:hover {
  transform: rotate(-10deg) scale(1.1); /* เอฟเฟกต์หมุนเล็กน้อย */
}

/* ลิงก์ในเมนู */
.nav-links {
  list-style: none;
  display: flex;
  gap: 25px;
  margin: 0;
  padding: 0;
}

.nav-links li {
  font-size: 1.1rem;
}

.nav-links a {
  text-decoration: none;
  color: white;
  font-weight: bold;
  padding: 10px 15px;
  border: 2px solid transparent; /* ขอบใส */
  border-radius: 50px; /* ขอบมน */
  transition: all 0.3s ease;
}

.nav-links a:hover {
  background: white;
  color: #ff4500;
  border: 2px solid #ff4500; /* เพิ่มเส้นขอบตอน hover */
}

/* Toggle Button (สำหรับมือถือ) */
.toggle-btn {
  display: none;
  font-size: 1.8rem;
  color: white;
  cursor: pointer;
}

/* Responsive Design */
@media (max-width: 768px) {
  .toggle-btn {
    display: block;
  }

  .nav-links {
    flex-direction: column;
    background: #ff4500;
    position: absolute;
    top: 100%;
    right: 0;
    width: 100%;
    display: none; /* ซ่อนเมนูเริ่มต้น */
    padding: 20px;
  }

  .nav-links.active {
    display: flex; /* แสดงเมนูเมื่อ active */
  }

  .nav-links li {
    text-align: center;
    margin-bottom: 15px;
  }
}
</style>