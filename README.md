# Ex09 Event Registration Web Application
## Date:17.11.2025

## AIM:
To design, develop and deploy a web application for event registration.

## DESIGN STEPS:

### Step 1:
Create a new frame.

### Step 2:
Select any one preset size of your choice.

### Step 3:
Select the shapes you need.

### Step 4:
Import images as needed.

### Step 5:
Create pages based on your need and link them.

### Step 6:

Validate the HTML and CSS code.

### Step 6:

Publish the website in the given URL.

## DESIGN TOOL:
Figma

## CODE:
```
import React from "react";
import screenshot202511202048482 from "./screenshot-2025-11-20-204848-2.png";

export const Iphone = (): JSX.Element => {
  return (
    <div className="bg-[#33bbf1] w-full min-w-[393px] min-h-[852px] relative">
      <img
        className="absolute top-2.5 left-0 w-[393px] h-[71px] aspect-[5.69] object-cover"
        alt="Saveetha Engineering College Header"
        src={screenshot202511202048482}
      />

      <h1 className="absolute top-[234px] left-[71px] [font-family:'IBM_Plex_Sans_Thai-Bold',Helvetica] font-bold text-white text-5xl tracking-[0] leading-[normal]">
        Hostel Fest
      </h1>

      <button
        className="absolute top-[596px] left-[71px] w-[235px] h-[85px] bg-[#ae74f5] cursor-pointer hover:bg-[#9d5fe6] transition-colors"
        aria-label="Register for Hostel Fest"
      >
        <span className="absolute top-[6px] left-0 w-full text-center [font-family:'IBM_Plex_Sans_Thai-Bold',Helvetica] font-bold text-white text-5xl tracking-[0] leading-[normal]">
          REGISTER
        </span>
      </button>
    </div>
  );
};

import React from "react";

const eventItems = [
  { id: 1, name: "singing" },
  { id: 2, name: "dancing" },
  { id: 3, name: "kho-kho" },
  { id: 4, name: "kabadi" },
];

export const Iphone = (): JSX.Element => {
  return (
    <div className="bg-[#42b9f0] w-full min-w-[393px] min-h-[852px] flex flex-col gap-[39px]">
      <header className="ml-[39px] w-[129px] h-[79px] mt-[25px]">
        <h1 className="[font-family:'IBM_Plex_Sans_Thai-Bold',Helvetica] font-bold text-white text-5xl tracking-[0] leading-[normal]">
          Event
        </h1>
      </header>

      <main className="ml-[75px] w-[259px] h-[316px]">
        <ol className="[font-family:'IBM_Plex_Sans_Thai-Bold',Helvetica] font-bold text-white text-5xl tracking-[0] leading-[normal]">
          {eventItems.map((item, index) => (
            <li key={item.id}>
              {item.name}
              {index < eventItems.length - 1 && <br />}
            </li>
          ))}
        </ol>
      </main>
    </div>
  );
};

import React, { useState } from "react";

export const Iphone = (): JSX.Element => {
  const [formData, setFormData] = useState({
    name: "",
    age: "",
    mobileNo: "",
    gender: "",
  });

  const handleInputChange = (
    e: React.ChangeEvent<HTMLInputElement | HTMLSelectElement>,
  ) => {
    const { name, value } = e.target;
    setFormData((prev) => ({
      ...prev,
      [name]: value,
    }));
  };

  const handleSubmit = (e: React.FormEvent) => {
    e.preventDefault();
    console.log("Form submitted:", formData);
  };

  return (
    <div className="bg-[#63b5fd] w-full min-w-[393px] min-h-[852px] relative">
      <header className="absolute top-2.5 left-[69px] [font-family:'IBM_Plex_Sans_Thai-Bold',Helvetica] font-bold text-black text-5xl tracking-[0] leading-[normal]">
        <h1>
          Registration
          <br />
          &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;form
        </h1>
      </header>

      <form
        onSubmit={handleSubmit}
        className="absolute top-[190px] left-0 w-full px-[49px]"
      >
        <div className="space-y-[48px]">
          <div className="flex items-center">
            <label
              htmlFor="name"
              className="[font-family:'IBM_Plex_Sans_Thai-Bold',Helvetica] font-bold text-black text-5xl tracking-[0] leading-[normal] w-[280px]"
            >
              Name
            </label>
            <input
              type="text"
              id="name"
              name="name"
              value={formData.name}
              onChange={handleInputChange}
              className="flex-1 bg-white/20 border-2 border-black/10 rounded-lg px-4 py-2 text-black text-2xl focus:outline-none focus:ring-2 focus:ring-black/20"
              aria-label="Name"
              required
            />
          </div>

          <div className="flex items-center">
            <label
              htmlFor="age"
              className="[font-family:'IBM_Plex_Sans_Thai-Bold',Helvetica] font-bold text-black text-5xl tracking-[0] leading-[normal] w-[280px]"
            >
              Age
            </label>
            <input
              type="number"
              id="age"
              name="age"
              value={formData.age}
              onChange={handleInputChange}
              className="flex-1 bg-white/20 border-2 border-black/10 rounded-lg px-4 py-2 text-black text-2xl focus:outline-none focus:ring-2 focus:ring-black/20"
              aria-label="Age"
              min="1"
              max="120"
              required
            />
          </div>

          <div className="flex items-center">
            <label
              htmlFor="mobileNo"
              className="[font-family:'IBM_Plex_Sans_Thai-Bold',Helvetica] font-bold text-black text-5xl tracking-[0] leading-[normal] w-[280px]"
            >
              Mobile no
            </label>
            <input
              type="tel"
              id="mobileNo"
              name="mobileNo"
              value={formData.mobileNo}
              onChange={handleInputChange}
              className="flex-1 bg-white/20 border-2 border-black/10 rounded-lg px-4 py-2 text-black text-2xl focus:outline-none focus:ring-2 focus:ring-black/20"
              aria-label="Mobile number"
              pattern="[0-9]{10}"
              required
            />
          </div>

          <div className="flex items-center">
            <label
              htmlFor="gender"
              className="[font-family:'IBM_Plex_Sans_Thai-Bold',Helvetica] font-bold text-black text-5xl tracking-[0] leading-[normal] w-[280px]"
            >
              Gender
            </label>
            <select
              id="gender"
              name="gender"
              value={formData.gender}
              onChange={handleInputChange}
              className="flex-1 bg-white/20 border-2 border-black/10 rounded-lg px-4 py-2 text-black text-2xl focus:outline-none focus:ring-2 focus:ring-black/20"
              aria-label="Gender"
              required
            >
              <option value="">Select</option>
              <option value="male">Male</option>
              <option value="female">Female</option>
              <option value="other">Other</option>
            </select>
          </div>
        </div>

        <button
          type="submit"
          className="absolute top-[487px] left-[-13px] [font-family:'IBM_Plex_Sans_Thai-Bold',Helvetica] font-bold text-black text-5xl tracking-[0] leading-[normal] bg-transparent hover:bg-black/10 transition-colors duration-200 px-4 py-2 rounded-lg focus:outline-none focus:ring-2 focus:ring-black/30"
          aria-label="Register Now"
        >
          Register Now
        </button>
      </form>
    </div>
  );
};

```
## OUTPUT:
![alt text](<Screenshot 2025-11-20 210848.png>)


## RESULT:
The program to design, develop and deploy a web application for event registration is completed successfully.
