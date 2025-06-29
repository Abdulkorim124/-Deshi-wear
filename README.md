import React from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";
import { Textarea } from "@/components/ui/textarea";

export default function HomePage() {
  return (
    <div className="min-h-screen bg-gradient-to-br from-white to-[#f9f9f9] p-4 md:p-10">
      <header className="text-center mb-10">
        <h1 className="text-4xl font-bold text-gray-800">DeshiWear</h1>
        <p className="text-gray-600 mt-2">স্টাইলিশ পাঞ্জাবি, পায়জামা ও দেশীয় পোশাকের অনলাইন দোকান</p>
      </header>

      <section className="grid grid-cols-1 md:grid-cols-3 gap-6 mb-12">
        {products.map((product, index) => (
          <Card key={index} className="rounded-2xl shadow-md">
            <img
              src={product.image}
              alt={product.name}
              className="rounded-t-2xl w-full h-60 object-cover"
            />
            <CardContent className="p-4">
              <h3 className="text-xl font-semibold text-gray-800">{product.name}</h3>
              <p className="text-gray-600 mb-2">{product.description}</p>
              <p className="text-lg font-bold text-green-600">৳ {product.price}</p>
              <Button className="mt-3 w-full bg-green-600 hover:bg-green-700 text-white">
                অর্ডার করুন
              </Button>
            </CardContent>
          </Card>
        ))}
      </section>

      <section className="max-w-2xl mx-auto bg-white p-6 rounded-2xl shadow-md">
        <h2 className="text-2xl font-bold text-center text-gray-800 mb-4">অর্ডার করুন</h2>
        <form className="grid grid-cols-1 gap-4">
          <Input type="text" placeholder="আপনার নাম" required />
          <Input type="tel" placeholder="মোবাইল নম্বর" required />
          <Input type="text" placeholder="ঠিকানা" required />
          <Textarea placeholder="পণ্যের নাম ও পরিমাণ লিখুন" required />
          <Button className="bg-green-600 hover:bg-green-700 text-white">অর্ডার সাবমিট করুন</Button>
        </form>
      </section>

      <footer className="text-center text-sm text-gray-500 mt-10">
        © 2025 DeshiWear. সমস্ত অধিকার সংরক্ষিত।
      </footer>
    </div>
  );
}

const products = [
  {
    name: "সাদা পাঞ্জাবি",
    description: "100% সুতি, আরামদায়ক ডিজাইন",
    price: 950,
    image: "https://i.ibb.co/DQGr2CH/panjabi1.jpg",
  },
  {
    name: "কালো পায়জামা",
    description: "স্লিম ফিট, ফ্যাশনেবল লুক",
    price: 750,
    image: "https://i.ibb.co/qm2W1Dp/paijama1.jpg",
  },
  {
    name: "ডিজাইন পাঞ্জাবি",
    description: "পার্টি লুক, উচ্চমানের ফেব্রিক",
    price: 1200,
    image: "https://i.ibb.co/0FYpCyH/panjabi2.jpg",
  },
];
