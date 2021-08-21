
nav {
  height: 20vh;
  width: 100%;
  background-image: linear-gradient(to right, #d8a706, #917602);
  color: rgb(0, 0, 0);
}
.navitems {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

.navitems h2 {
  font-size: 30px;
}

.navitems button {
  width: 30%;
  height: 10vh;
  border: 2px solid transparent;
  border-radius: 30px;
  background-color: #a5e000;
  font-family: serif;
  font-size: 20px;
  margin: auto 0px;
}

.fetchbtn:hover {
  background-color: rgb(255, 238, 0);
}
.userdatacontainer {
  width: 100%;
  height: fit-content;
  background-image: linear-gradient(to bottom right, #01461b, #64c9cf);
}
#main {
  flex-wrap: wrap;
  justify-content: space-around;
  align-items: center;
  overflow: hidden;
}
.name:hover {
  color: rgb(17, 255, 9);
}

.avatar {
  border-radius: 20%;
}

.profile_cont {
  border-radius: 15%;
  background-image: radial-gradient(#06a02c, #074211);
  margin: 5px;
  padding: 10px;
  width: 30%;
  text-align: center;
  transition: transform ease 0.2s;
  opacity: 0.8;
  margin-top: 8vh;
}

.profile_cont:hover {
  transform: scale(1.2);
  opacity: 1;
}

.footer {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
}
