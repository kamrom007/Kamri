import React, {useState, useEffect} from 'react'
import axios from 'axios'

const Getlesson = () => {

     const  [users, Setusers] = useState([])

     useEffect(() => {
        axios.get("https://jsonplaceholder.typicode.com/users")
        .then(res => {
            Setusers(res.data);
            console.log(res);
        })
  
        .catch(err => {
            console.error("Error!");
        })

     }, [])


  return (
    <div>
        {users.map(user => (
            <div className='infos'>
                <h1>{user.name}</h1>
                <h2></h2>

            </div>
        ))}
        <h1>Kamron</h1>
    </div>
  )
}

export default Getlesson
