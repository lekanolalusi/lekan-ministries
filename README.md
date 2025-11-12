import React from "react";
import { motion } from "framer-motion";
import {
  Mail,
  Phone,
  MapPin,
  Heart,
  Music,
  BookOpen,
  Users,
  Calendar,
} from "lucide-react";

// Single-file React component for a ministry website built with TailwindCSS
// Instructions: drop this into a React app (Create React App / Next.js). Tailwind, framer-motion
// and lucide-react should be installed. Replace placeholder assets and links with your real
// images/audio and text. This file focuses on structure, accessibility and a modern aesthetic.

const ministries = [
  {
    id: "exchange",
    title: "Exchange Place",
    tagline: "Worship, community and prophetic gatherings",
    description:
      "Exchange Place is our flagship worship movement — a place for lively worship, teaching and community activation. We gather people to encounter God and to be sent into kingdom influence.",
    icon: Users,
  },
  {
    id: "beyond",
    title: "Beyond Bars",
    tagline: "Prison ministry & restoration",
    description:
      "Beyond Bars brings the gospel into correctional facilities, offering discipleship, practical support and restorative programs for those re-entering society.",
    icon: Heart,
  },
  {
    id: "music",
    title: "Music Ministry",
    tagline: "Worship recordings, live sessions & creative arts",
    description:
      "A catalogue of songs, live worship recordings and artistic projects — music meant to minister and transform. Discover recent singles, albums and music videos.",
    icon: Music,
  },
  {
    id: "teaching",
    title: "Teaching & Resources",
    tagline: "Sermons, courses and study guides",
    description:
      "Biblical teaching, short series and downloadable resources designed to deepen spiritual understanding and practical holiness.",
    icon: BookOpen,
  },
];

const upcomingEvents = [
  {
    date: "2026-01-17",
    title: "Exchange Place Worship - New Year Gathering",
    location: "Main Auditorium, Exchange Place",
  },
  {
    date: "2026-03-21",
    title: "Beyond Bars — Volunteer Training",
    location: "Community Center, Newark, NJ",
  },
];

export default function LekanOlalusiMinistriesSite() {
  return (
    <div className="min-h-screen bg-gradient-to-b from-white via-slate-50 to-sky-50 text-slate-900">
      <header className="sticky top-0 z-40 backdrop-blur bg-white/60 border-b border-slate-200">
        <div className="max-w-6xl mx-auto px-6 py-4 flex items-center justify-between">
          <a href="#home" className="flex items-center gap-3">
            <div className="h-10 w-10 rounded-lg bg-gradient-to-br from-sky-500 via-slate-300 to-white shadow-md flex items-center justify-center text-white font-bold">LO</div>
            <div>
              <div className="text-lg font-semibold">Lekan Olalusi Ministries</div>
              <div className="text-xs text-slate-500">Exchange Place • Beyond Bars • Music • Teaching</div>
            </div>
          </a>

          <nav className="hidden md:flex items-center gap-6 text-sm">
            <a href="#ministries" className="hover:underline">Ministries</a>
            <a href="#music" className="hover:underline">Music</a>
            <a href="#events" className="hover:underline">Events</a>
            <a href="#resources" className="hover:underline">Resources</a>
            <a href="#connect" className="px-4 py-2 rounded-md bg-sky-600 text-white">Get Involved</a>
          </nav>

          <div className="md:hidden">
            {/* small-screen simple menu placeholder - replace with a working mobile menu if needed */}
            <a href="#connect" className="px-3 py-2 rounded-md bg-sky-600 text-white text-sm">Connect</a>
          </div>
        </div>
      </header>

      <main id="home">
        <section className="max-w-6xl mx-auto px-6 py-16 grid md:grid-cols-2 gap-8 items-center">
          <motion.div initial={{ x: -30, opacity: 0 }} animate={{ x: 0, opacity: 1 }} transition={{ duration: 0.6 }}>
            <h1 className="text-4xl md:text-5xl font-extrabold leading-tight">Lekan Olalusi Ministries</h1>
            <p className="mt-4 text-lg text-slate-700">A movement of worship, restoration and apostolic teaching. We pursue God, raise worshipers and release leaders to minister in every sphere of life.</p>

            <div className="mt-6 flex gap-4">
              <a href="#ministries" className="px-5 py-3 rounded-md bg-sky-600 text-white font-medium">Explore Ministries</a>
              <a href="#music" className="px-5 py-3 rounded-md border border-slate-300">Listen to Music</a>
            </div>

            <div className="mt-8 grid grid-cols-2 gap-3 text-sm text-slate-600">
              <div className="flex items-start gap-2">
                <MapPin size={16} /> <span>New Jersey • Home base</span>
              </div>
              <div className="flex items-start gap-2">
                <Mail size={16} /> <span>hello@lekanolalusi.org (placeholder)</span>
              </div>
            </div>

          </motion.div>

          <motion.div initial={{ scale: 0.98, opacity: 0 }} animate={{ scale: 1, opacity: 1 }} transition={{ duration: 0.6 }} className="rounded-2xl overflow-hidden shadow-xl bg-white">
            {/* Replace with a hero media — image, video or animated slide */}
            <div className="h-80 bg-[url('/hero-placeholder.jpg')] bg-cover bg-center flex items-end p-6">
              <div className="bg-white/80 p-3 rounded-md">"Worship. Teach. Restore. Send."</div>
            </div>
          </motion.div>
        </section>

        <section id="ministries" className="max-w-6xl mx-auto px-6 py-12">
          <h2 className="text-2xl font-bold">Our Ministries</h2>
          <p className="mt-2 text-slate-600">A short overview of the core ministries under Lekan Olalusi Ministries.</p>

          <div className="mt-6 grid sm:grid-cols-2 lg:grid-cols-4 gap-6">
            {ministries.map((m) => (
              <article key={m.id} className="p-5 bg-white shadow rounded-lg">
                <div className="flex items-center gap-3">
                  <div className="p-3 rounded-md bg-sky-50">
                    <m.icon size={28} className="text-sky-600" />
                  </div>
                  <div>
                    <h3 className="font-semibold">{m.title}</h3>
                    <div className="text-sm text-slate-500">{m.tagline}</div>
                  </div>
                </div>
                <p className="mt-4 text-sm text-slate-600">{m.description}</p>
                <div className="mt-4 flex gap-3">
                  <a href={`#${m.id}`} className="text-sm underline">Learn more</a>
                  <a href="#connect" className="text-sm">Get involved</a>
                </div>
              </article>
            ))}
          </div>
        </section>

        <section id="music" className="max-w-6xl mx-auto px-6 py-12">
          <div className="grid md:grid-cols-2 gap-8">
            <div className="rounded-lg overflow-hidden bg-white shadow p-6">
              <h3 className="text-xl font-semibold flex items-center gap-2"><Music size={18}/> Music Ministry</h3>
              <p className="mt-2 text-slate-600">Discover singles, albums and live worship recordings. Stream or download from your favourite platforms.</p>

              <div className="mt-6">
                {/* Placeholder audio playlist — replace with embedded player (Spotify, Soundcloud or custom audio component) */}
                <div className="border rounded-md p-4">
                  <div className="text-sm font-medium">Latest Single: "Sacrifice"</div>
                  <div className="mt-3 text-sm text-slate-500">Release: 2025</div>
                  <div className="mt-4 flex gap-2">
                    <button className="px-3 py-2 rounded bg-sky-600 text-white">Play</button>
                    <button className="px-3 py-2 rounded border">Buy / Stream</button>
                  </div>
                </div>
              </div>
            </div>

            <div className="rounded-lg overflow-hidden bg-white shadow p-6">
              <h3 className="text-xl font-semibold flex items-center gap-2"><BookOpen size={18}/> Teaching & Media</h3>
              <p className="mt-2 text-slate-600">Sermons, teaching series and downloadable study guides. Short films and trailers accompany seasonal campaigns and albums.</p>
              <div className="mt-4 grid grid-cols-1 gap-3">
                <a className="p-3 border rounded">Latest Sermon: "Spiritual Intelligence" — watch</a>
                <a className="p-3 border rounded">Short Film: "Wilderness Cry" — trailer</a>
              </div>
            </div>
          </div>
        </section>

        <section id="events" className="max-w-6xl mx-auto px-6 py-12">
          <h2 className="text-2xl font-bold">Upcoming Events</h2>
          <div className="mt-6 grid md:grid-cols-2 gap-6">
            {upcomingEvents.map((e) => (
              <div key={e.title} className="p-5 bg-white rounded-lg shadow flex items-start gap-4">
                <div className="text-sm text-slate-500">
                  <div className="text-lg font-semibold">{new Date(e.date).toLocaleDateString()}</div>
                  <div className="text-xs">{e.location}</div>
                </div>
                <div>
                  <div className="font-semibold">{e.title}</div>
                  <div className="mt-2 text-sm text-slate-600">Description placeholder — add event details, registration link and volunteer info.</div>
                  <div className="mt-3 flex gap-2">
                    <a className="text-sm px-3 py-2 rounded bg-sky-600 text-white">Register</a>
                    <a className="text-sm px-3 py-2 rounded border">Volunteer</a>
                  </div>
                </div>
              </div>
            ))}
          </div>
        </section>

        <section id="resources" className="max-w-6xl mx-auto px-6 py-12">
          <div className="grid md:grid-cols-3 gap-6">
            <div className="bg-white p-6 rounded-lg shadow">
              <h4 className="font-semibold">Sermons & Series</h4>
              <p className="mt-2 text-sm text-slate-600">Stream or download recent teaching series and sermon notes.</p>
              <a className="mt-4 inline-block text-sm underline">See library</a>
            </div>

            <div className="bg-white p-6 rounded-lg shadow">
              <h4 className="font-semibold">Beyond Bars Resources</h4>
              <p className="mt-2 text-sm text-slate-600">Volunteer guides, prison visitation policies and rehabilitation programs.
              </p>
              <a className="mt-4 inline-block text-sm underline">Learn more</a>
            </div>

            <div className="bg-white p-6 rounded-lg shadow">
              <h4 className="font-semibold">Creative & Media</h4>
              <p className="mt-2 text-sm text-slate-600">Artwork, music videos and behind-the-scenes for creative projects like Moroti and album rollouts.</p>
              <a className="mt-4 inline-block text-sm underline">Media Kit</a>
            </div>
          </div>
        </section>

        <section id="connect" className="max-w-6xl mx-auto px-6 py-12">
          <div className="grid md:grid-cols-2 gap-8">
            <div className="bg-white p-6 rounded-lg shadow">
              <h3 className="font-semibold text-xl">Get Involved</h3>
              <p className="mt-2 text-slate-600">Join a ministry team, volunteer with Beyond Bars, or partner with us financially to support the work.
              </p>

              <div className="mt-4 grid gap-3">
                <a className="p-3 rounded bg-sky-600 text-white inline-block w-max">Volunteer</a>
                <a className="p-3 rounded border inline-block w-max">Partner / Donate</a>
                <a className="p-3 rounded border inline-block w-max">Request Prayer</a>
              </div>
            </div>

            <div className="bg-white p-6 rounded-lg shadow">
              <h3 className="font-semibold text-xl">Contact & Connect</h3>
              <form className="mt-4 grid gap-3">
                <input className="border p-3 rounded" placeholder="Full name" />
                <input className="border p-3 rounded" placeholder="Email" />
                <textarea className="border p-3 rounded" placeholder="Message" rows={4} />
                <div className="flex gap-2">
                  <button className="px-4 py-2 rounded bg-sky-600 text-white">Send Message</button>
                  <button type="button" className="px-4 py-2 rounded border">Call Office</button>
                </div>
              </form>

              <div className="mt-6 text-sm text-slate-600 grid gap-2">
                <div className="flex items-center gap-2"><Phone size={14}/> +1 (555) 123-4567 (placeholder)</div>
                <div className="flex items-center gap-2"><Mail size={14}/> hello@lekanolalusi.org</div>
                <div className="flex items-center gap-2"><MapPin size={14}/> New Jersey, USA</div>
              </div>
            </div>
          </div>
        </section>

      </main>

      <footer className="border-t mt-12 bg-white">
        <div className="max-w-6xl mx-auto px-6 py-8 flex flex-col md:flex-row justify-between items-start gap-6">
          <div>
            <div className="text-lg font-semibold">Lekan Olalusi Ministries</div>
            <div className="text-sm text-slate-600 mt-1">Leading worship, restoring lives and releasing apostolic influence.</div>
          </div>

          <div className="flex gap-6">
            <div>
              <div className="text-sm font-semibold">Quick Links</div>
              <ul className="mt-2 text-sm text-slate-600">
                <li><a href="#ministries">Ministries</a></li>
                <li><a href="#events">Events</a></li>
                <li><a href="#connect">Contact</a></li>
              </ul>
            </div>

            <div>
              <div className="text-sm font-semibold">Legal</div>
              <ul className="mt-2 text-sm text-slate-600">
                <li><a>Privacy</a></li>
                <li><a>Terms</a></li>
              </ul>
            </div>
          </div>

        </div>
        <div className="text-center text-xs text-slate-500 py-4">© {new Date().getFullYear()} Lekan Olalusi Ministries. All rights reserved.</div>
      </footer>
    </div>
  );
}
