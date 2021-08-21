app.css
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


app.js
import Users from "./components/cards";
import "./App.css";
import React, { Component } from "react";

class App extends Component {
  constructor(props) {
    super(props);

    this.state = { users_data: [], loading: false };

    this.updateState = this.updateState.bind(this);
  }

  updateState() {
    this.setState({ loading: true });

    setTimeout(
      async function () {
        const response = await fetch("https://reqres.in/api/users?page=1");
        const jsonresponse = await response.json();
        console.log(jsonresponse);
        this.setState({ users_data: jsonresponse["data"], loading: false });
      }.bind(this),
      2000
    );
  }

  render() {
    return (
      <>
        <nav className="navbar">
          <div className="navitems">
            <h2>WELCOME TO GET THE USER</h2>
            <button className="fetchbtn" onClick={this.updateState}>
              Get Users
            </button>
          </div>
        </nav>
        <div className="userdatacontainer">
          <Users loading={this.state.loading} users={this.state.users_data} />
        </div>
        <footer className="footer">Click on the Button to get the user</footer>
      </>
    );
  }
}

export default App;


cards.js
import React from "react";

const Users = ({ loading, users }) => {
  const mainstyle = {
    display: "flex"
  };
  return loading ? (
    <div id="main" align="Middle">
      <img
        src="http://media.giphy.com/media/s4KqhlPU9Ypnq/giphy.gif"
        alt="Loading.."
        className="loader"
      />
    </div>
  ) : (
    <div id="main" style={mainstyle}>
      {users.map((user) => (
        <div className="profile_cont" key={user.id}>
          {console.log(user)}

          <img src={user.avatar} alt={user.avatar} className="avatar"></img>
          <h1 className="name">
            {user.first_name} {user.last_name}
          </h1>
          <p className="email">{user.email}</p>
          <p>User ID: {user.id}</p>
        </div>
      ))}
    </div>
  );
};


index.css
body {
  margin: 0;
  font-family: Impact, Haettenschweiler, "Arial Narrow Bold", sans-serif;

  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}


index.js
import React from "react";
import ReactDOM from "react-dom";
import "./index.css";
import App from "./App";
import reportWebVitals from "./reportWebVitals";

ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById("root")
);

reportWebVitals();

reportWebVitals.js
const reportWebVitals = (onPerfEntry) => {
  if (onPerfEntry && onPerfEntry instanceof Function) {
    import("web-vitals").then(({ getCLS, getFID, getFCP, getLCP, getTTFB }) => {
      getCLS(onPerfEntry);
      getFID(onPerfEntry);
      getFCP(onPerfEntry);
      getLCP(onPerfEntry);
      getTTFB(onPerfEntry);
    });
  }
};

export default reportWebVitals;

setup.js
import "@testing-library/jest-dom";


Output link
https://jrer4.csb.app/
