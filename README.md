# Thermalconnect
import { useState } from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Phone, Bus, Car, Users } from "lucide-react";
import { motion } from "framer-motion";
import Image from "next/image";

export default function ThermalConnect() {
  const [activeTab, setActiveTab] = useState("home");

  const sections = {
    home: (
      <Card className="p-4 rounded-2xl shadow-md">
        <CardContent>
          <h1 className="text-xl font-bold text-center mb-2">Thermal Connect</h1>
          <p className="text-center text-base mb-4">
            Ab Bokaro Thermal (829107) me car rent aur bus ki jankari online.
            Safar ab hoga aur bhi aasan!
          </p>
          <div className="grid grid-cols-2 gap-4">
            <Button onClick={() => setActiveTab("cars")} className="rounded-2xl">
              <Car className="mr-2 h-4 w-4" /> Car Rent
            </Button>
            <Button onClick={() => setActiveTab("buses")} className="rounded-2xl">
              <Bus className="mr-2 h-4 w-4" /> Bus Info
            </Button>
          </div>
        </CardContent>
      </Card>
    ),
    cars: (
      <Card className="p-4 rounded-2xl shadow-md">
        <CardContent>
          <h2 className="text-lg font-bold mb-2">Car Chahiye? Yahan Book Kijiye!</h2>
          <div className="grid grid-cols-2 gap-4 mb-4">
            <Image src="/car1.jpg" alt="Car 1" width={200} height={120} className="rounded-2xl" />
            <Image src="/car2.jpg" alt="Car 2" width={200} height={120} className="rounded-2xl" />
          </div>
          <ul className="list-disc list-inside text-base space-y-1">
            <li>Local car owners apni gaadi register karte hain.</li>
            <li>Ab gaadi lene ke liye station ya chowk nahi jana hoga.</li>
            <li>Sirf call kijiye, driver aapke ghar aa jayega.</li>
          </ul>
          <Button className="w-full mt-4 rounded-2xl">
            <Phone className="mr-2 h-4 w-4" /> Booking ke liye Call karein
          </Button>
        </CardContent>
      </Card>
    ),
    buses: (
      <Card className="p-4 rounded-2xl shadow-md">
        <CardContent>
          <h2 className="text-lg font-bold mb-2">Bus Kab Chalegi? Yahan Dekhiye!</h2>
          <p className="text-base mb-2">
            Bokaro Thermal se chalne wali buses ka time aur route.
          </p>
          <ul className="list-disc list-inside text-base space-y-1">
            <li>Ranchi, Bokaro, Dhanbad, Ramgarh ke liye buses.</li>
            <li>Updated time aur contact number milega.</li>
            <li>Ab bus station me wait karna nahi padega.</li>
          </ul>
          <Button className="w-full mt-4 rounded-2xl">
            <Bus className="mr-2 h-4 w-4" /> Bus Time Table Dekhein
          </Button>
        </CardContent>
      </Card>
    ),
    owners: (
      <Card className="p-4 rounded-2xl shadow-md">
        <CardContent>
          <h2 className="text-lg font-bold mb-2">Apna Business Online Layein</h2>
          <p className="text-base mb-2">
            Car ya bus owners apni service yahan register karke zyada customers tak
            pahunchein.
          </p>
          <ul className="list-disc list-inside text-base space-y-1">
            <li>Free listing – koi extra paisa nahi.</li>
            <li>Aapka number seedha local logon ko dikhai dega.</li>
            <li>Bokaro Thermal ke liye safar aasan banaiye.</li>
          </ul>
          <Button className="w-full mt-4 rounded-2xl">
            <Users className="mr-2 h-4 w-4" /> Register Karein
          </Button>
        </CardContent>
      </Card>
    ),
    contact: (
      <Card className="p-4 rounded-2xl shadow-md">
        <CardContent>
          <h2 className="text-lg font-bold mb-2">Contact Us</h2>
          <p className="text-base">
            📍 Location: Bokaro Thermal, Jharkhand – 829107
            <br />
            📞 Helpline / WhatsApp: +91-XXXXXXXXXX
            <br />
            🌐 Website: www.thermalconnect.in
          </p>
        </CardContent>
      </Card>
    ),
  };

  return (
    <motion.div
      initial={{ opacity: 0 }}
      animate={{ opacity: 1 }}
      className="p-4 max-w-md mx-auto space-y-4"
    >
      {sections[activeTab]}

      <div className="flex justify-around fixed bottom-0 left-0 right-0 bg-white p-2 shadow-inner">
        <Button variant={activeTab === "home" ? "default" : "outline"} onClick={() => setActiveTab("home")} className="rounded-2xl">Home</Button>
        <Button variant={activeTab === "cars" ? "default" : "outline"} onClick={() => setActiveTab("cars")} className="rounded-2xl">Cars</Button>
        <Button variant={activeTab === "buses" ? "default" : "outline"} onClick={() => setActiveTab("buses")} className="rounded-2xl">Buses</Button>
        <Button variant={activeTab === "owners" ? "default" : "outline"} onClick={() => setActiveTab("owners")} className="rounded-2xl">Owners</Button>
        <Button variant={activeTab === "contact" ? "default" : "outline"} onClick={() => setActiveTab("contact")} className="rounded-2xl">Contact</Button>
      </div>
    </motion.div>
  );
}
