import React, { useState } from "react";

function StudentForm() {
  const [formData, setFormData] = useState({
    name: "",
    age: "",
    class: ""
  });

  const handleChange = (e) => {
    setFormData({ ...formData, [e.target.name]: e.target.value });
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    alert(Submitted: ${formData.name}, ${formData.age}, ${formData.class});
  };

  return (
    <div className="max-w-md mx-auto mt-10 p-6 border rounded-2xl shadow">
      <h2 className="text-2xl font-semibold mb-4 text-center">Student Form</h2>
      <form onSubmit={handleSubmit} className="space-y-4">
        <input
          type="text"
          name="name"
          placeholder="Enter name"
          value={formData.name}
          onChange={handleChange}
          className="w-full p-2 border rounded"
          required
        />
        <input
          type="number"
          name="age"
          placeholder="Enter age"
          value={formData.age}
          onChange={handleChange}
          className="w-full p-2 border rounded"
          required
        />
        <input
          type="text"
          name="class"
          placeholder="Enter class"
          value={formData.class}
          onChange={handleChange}
          className="w-full p-2 border rounded"
          required
        />
        <button
          type="submit"
          className="w-full bg-blue-600 text-white py-2 rounded hover:bg-blue-700"
        >
          Submit
        </button>
      </form>
    </div>
  );

  import React from "react";
import { BrowserRouter as Router, Routes, Route, Link } from "react-router-dom";
import StudentForm from "./StudentForm";

function App() {
  return (
    <Router>
      <nav className="p-4 bg-gray-100">
        <Link to="/studentform" className="text-blue-600 font-medium">
          Go to Student Form
        </Link>
      </nav>

      <Routes>
        <Route path="/studentform" element={<StudentForm />} />
      </Routes>
    </Router>
  );
}

export default App;
}

export default StudentForm;
