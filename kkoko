import { useState } from "react";

const data = {
  catering: [
    { day: "Day 0", date: "Sun 19 Jul", label: "Arrival", breakfast: null, lunch: null, packed: null, dinner: 70, special: null, note: null },
    { day: "Day 1", date: "Mon 20 Jul", label: null, breakfast: 70, lunch: 70, packed: null, dinner: 70, special: null, note: null },
    { day: "Day 2", date: "Tue 21 Jul", label: null, breakfast: 70, lunch: 70, packed: null, dinner: 70, special: null, note: null },
    { day: "Day 3", date: "Wed 22 Jul", label: "Excursion", breakfast: 70, lunch: null, packed: 70, dinner: null, special: null, note: "Early breakfast by 7am · Dinner off-site" },
    { day: "Day 4", date: "Thu 23 Jul", label: "Sport Science", breakfast: 70, lunch: 70, packed: null, dinner: 70, special: null, note: null },
    { day: "Day 5", date: "Fri 24 Jul", label: "Campus Discovery", breakfast: 70, lunch: 70, packed: null, dinner: 70, special: null, note: null },
    { day: "Day 6", date: "Sat 25 Jul", label: "Manchester", breakfast: 70, lunch: null, packed: 70, dinner: null, special: null, note: "Early breakfast by 7am · Dinner off-site" },
    { day: "Day 7", date: "Sun 26 Jul", label: "Career Exploration", breakfast: 70, lunch: 70, packed: null, dinner: null, special: null, note: "Dinner in town" },
    { day: "Day 8", date: "Mon 27 Jul", label: null, breakfast: 70, lunch: 70, packed: null, dinner: 70, special: null, note: null },
    { day: "Day 9", date: "Tue 28 Jul", label: null, breakfast: 70, lunch: 70, packed: null, dinner: 70, special: null, note: null },
    { day: "Day 10", date: "Wed 29 Jul", label: "Cardiff", breakfast: 70, lunch: null, packed: 70, dinner: null, special: null, note: "Early breakfast by 7am · Dinner off-site" },
    { day: "Day 11", date: "Thu 30 Jul", label: "Sports Science Lab", breakfast: 70, lunch: 70, packed: null, dinner: 70, special: null, note: null },
    { day: "Day 12", date: "Fri 31 Jul", label: "Graduation", breakfast: 70, lunch: 70, packed: null, dinner: null, special: 70, note: "Graduation Dinner" },
    { day: "Day 13", date: "Sat 1 Aug", label: "Departure", breakfast: 70, lunch: null, packed: null, dinner: null, special: null, note: null },
  ],
  totals: [
    { label: "Breakfast", days: 13, covers: 910, color: "#F59E0B" },
    { label: "Lunch (on-site)", days: 10, covers: 700, color: "#10B981" },
    { label: "Packed Lunch", days: 3, covers: 210, color: "#6366F1" },
    { label: "Dinner (on-site)", days: 8, covers: 560, color: "#EC4899" },
    { label: "Graduation Dinner", days: 1, covers: 70, color: "#8B5CF6" },
  ],
  venue: [
    { title: "Arrival Day – The Lounge", date: "Sun 19 Jul", time: "2:00pm – 9:00pm", details: "Social & hangout space during check-in and orientation" },
    { title: "Evening Socials – The Lounge", date: "10 evenings", time: "7:00pm – 9:00pm", details: "AV tech (screen, speakers, mic) required for 3 evenings (dates TBC)" },
    { title: "Graduation & Disco – The Basement", date: "Fri 31 Jul", time: "2:00pm – 11:00pm", details: "Ceremony, sit-down dinner, disco · AV & DJ · Decorations · Photo booth · Live performance" },
  ],
  quoteItems: [
    "Breakfast – per head/day (×910 covers)",
    "Standard lunch – per head/day (×700 covers)",
    "Packed lunch – per head/day (×210 covers)",
    "Standard dinner – per head/day (×560 covers)",
    "Graduation Dinner – per head or fixed (70 guests)",
    "Venue: Arrival day Lounge – Sun 19 Jul, 2–9pm",
    "Venue: Evening socials Lounge – 10 evenings, 7–9pm",
    "AV tech hire – per evening (3 evenings TBC)",
    "Venue: Graduation Basement – Fri 31 Jul, 2–11pm",
    "Graduation venue decorations",
    "DJ hire – Fri 31 Jul",
    "Photo booth hire – Fri 31 Jul",
    "Live performance – Fri 31 Jul (options/availability)",
  ]
};

const Pill = ({ active, children, onClick }) => (
  <button
    onClick={onClick}
    style={{
      padding: "8px 20px",
      borderRadius: "100px",
      border: "none",
      background: active ? "#1a1a1a" : "#f5f5f5",
      color: active ? "#fff" : "#666",
      fontSize: "13px",
      fontWeight: 500,
      cursor: "pointer",
      transition: "all 0.2s ease",
      letterSpacing: "0.01em"
    }}
  >
    {children}
  </button>
);

const Dot = ({ color, active }) => (
  <span style={{
    display: "inline-block",
    width: 8,
    height: 8,
    borderRadius: "50%",
    background: active ? color : "#e0e0e0",
    transition: "all 0.3s ease"
  }} />
);

const Card = ({ children, style }) => (
  <div style={{
    background: "#fff",
    borderRadius: 16,
    padding: "24px 28px",
    border: "1px solid #f0f0f0",
    ...style
  }}>
    {children}
  </div>
);

export default function App() {
  const [tab, setTab] = useState("overview");
  const [hoveredDay, setHoveredDay] = useState(null);
  const grandTotal = data.totals.reduce((s, t) => s + t.covers, 0);
  const maxCovers = Math.max(...data.totals.map(t => t.covers));

  return (
    <div style={{
      fontFamily: "'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif",
      maxWidth: 720,
      margin: "0 auto",
      padding: "48px 24px",
      color: "#1a1a1a",
      background: "#fafafa",
      minHeight: "100vh"
    }}>
      {/* Header */}
      <div style={{ marginBottom: 48 }}>
        <p style={{ fontSize: 11, fontWeight: 600, letterSpacing: "0.12em", textTransform: "uppercase", color: "#999", margin: "0 0 12px" }}>
          Innovation Academy × Loughborough SU
        </p>
        <h1 style={{ fontSize: 28, fontWeight: 700, margin: "0 0 8px", lineHeight: 1.2, letterSpacing: "-0.02em" }}>
          Service Requirements
        </h1>
        <p style={{ fontSize: 15, color: "#888", margin: 0, lineHeight: 1.5 }}>
          Summer 2026 · 19 July – 1 August · 70 people
        </p>
      </div>

      {/* Stats */}
      <div style={{ display: "grid", gridTemplateColumns: "1fr 1fr 1fr", gap: 12, marginBottom: 36 }}>
        {[
          { n: "14", l: "Days" },
          { n: "2,450", l: "Total Covers" },
          { n: "13", l: "Quote Items" },
        ].map((s, i) => (
          <Card key={i} style={{ textAlign: "center", padding: "20px 16px" }}>
            <div style={{ fontSize: 24, fontWeight: 700, letterSpacing: "-0.02em" }}>{s.n}</div>
            <div style={{ fontSize: 11, color: "#999", marginTop: 4, fontWeight: 500, textTransform: "uppercase", letterSpacing: "0.06em" }}>{s.l}</div>
          </Card>
        ))}
      </div>

      {/* Tabs */}
      <div style={{ display: "flex", gap: 8, marginBottom: 32, flexWrap: "wrap" }}>
        {[
          ["overview", "Overview"],
          ["schedule", "Day-by-Day"],
          ["venue", "Venue Hire"],
          ["quote", "Quote Items"],
        ].map(([k, l]) => (
          <Pill key={k} active={tab === k} onClick={() => setTab(k)}>{l}</Pill>
        ))}
      </div>

      {/* Overview */}
      {tab === "overview" && (
        <div style={{ display: "flex", flexDirection: "column", gap: 16 }}>
          <Card>
            <h3 style={{ fontSize: 13, fontWeight: 600, textTransform: "uppercase", letterSpacing: "0.08em", color: "#999", margin: "0 0 20px" }}>Catering Totals</h3>
            <div style={{ display: "flex", flexDirection: "column", gap: 16 }}>
              {data.totals.map((t, i) => (
                <div key={i}>
                  <div style={{ display: "flex", justifyContent: "space-between", marginBottom: 6 }}>
                    <span style={{ fontSize: 14, fontWeight: 500 }}>{t.label}</span>
                    <span style={{ fontSize: 14, color: "#666" }}>{t.covers.toLocaleString()} covers · {t.days} days</span>
                  </div>
                  <div style={{ height: 6, background: "#f0f0f0", borderRadius: 3, overflow: "hidden" }}>
                    <div style={{
                      height: "100%",
                      width: `${(t.covers / maxCovers) * 100}%`,
                      background: t.color,
                      borderRadius: 3,
                      transition: "width 0.6s ease"
                    }} />
                  </div>
                </div>
              ))}
            </div>
            <div style={{ borderTop: "1px solid #f0f0f0", marginTop: 20, paddingTop: 16, display: "flex", justifyContent: "space-between" }}>
              <span style={{ fontSize: 14, fontWeight: 600 }}>Grand Total</span>
              <span style={{ fontSize: 14, fontWeight: 600 }}>{grandTotal.toLocaleString()} covers</span>
            </div>
          </Card>

          <Card>
            <h3 style={{ fontSize: 13, fontWeight: 600, textTransform: "uppercase", letterSpacing: "0.08em", color: "#999", margin: "0 0 16px" }}>Meal Style</h3>
            <p style={{ fontSize: 14, lineHeight: 1.7, color: "#555", margin: 0 }}>
              Buffet-style with set menus. Each service includes a hot main dish with smaller sides and grazing options — fruit salads, mixed salad bowls, cold pasta, bread rolls, hummus, vegetable sticks, and yoghurt pots. Designed to encourage variety across an international group. Happy to collaborate with the kitchen manager on menus.
            </p>
          </Card>

          <Card>
            <h3 style={{ fontSize: 13, fontWeight: 600, textTransform: "uppercase", letterSpacing: "0.08em", color: "#999", margin: "0 0 16px" }}>Key Notes</h3>
            <div style={{ display: "flex", flexDirection: "column", gap: 10 }}>
              {[
                "Early breakfast (by 7am) on 3 excursion days",
                "Packed lunches ready for collection by 7:30am",
                "4 evenings with no dinner on-site (off-site excursions + town)",
                "Dietary & allergen requirements confirmed closer to date",
              ].map((n, i) => (
                <div key={i} style={{ display: "flex", gap: 10, alignItems: "flex-start" }}>
                  <span style={{ color: "#ccc", fontSize: 14, lineHeight: "22px" }}>→</span>
                  <span style={{ fontSize: 14, color: "#555", lineHeight: "22px" }}>{n}</span>
                </div>
              ))}
            </div>
          </Card>
        </div>
      )}

      {/* Schedule */}
      {tab === "schedule" && (
        <Card>
          <div style={{ display: "flex", gap: 16, marginBottom: 20, flexWrap: "wrap" }}>
            {data.totals.map((t, i) => (
              <div key={i} style={{ display: "flex", alignItems: "center", gap: 6 }}>
                <span style={{ width: 8, height: 8, borderRadius: "50%", background: t.color, display: "inline-block" }} />
                <span style={{ fontSize: 11, color: "#888" }}>{t.label}</span>
              </div>
            ))}
          </div>
          <div style={{ display: "flex", flexDirection: "column", gap: 2 }}>
            {data.catering.map((d, i) => {
              const isHovered = hoveredDay === i;
              return (
                <div
                  key={i}
                  onMouseEnter={() => setHoveredDay(i)}
                  onMouseLeave={() => setHoveredDay(null)}
                  style={{
                    display: "grid",
                    gridTemplateColumns: "100px 90px 1fr",
                    alignItems: "center",
                    padding: "10px 12px",
                    borderRadius: 10,
                    background: isHovered ? "#f8f8f8" : "transparent",
                    transition: "background 0.15s ease",
                    cursor: "default"
                  }}
                >
                  <div>
                    <div style={{ fontSize: 13, fontWeight: 600 }}>{d.day}</div>
                    {d.label && <div style={{ fontSize: 10, color: "#999", fontWeight: 500, marginTop: 1 }}>{d.label}</div>}
                  </div>
                  <div style={{ fontSize: 12, color: "#999" }}>{d.date}</div>
                  <div style={{ display: "flex", alignItems: "center", gap: 8 }}>
                    <div style={{ display: "flex", gap: 6 }}>
                      <Dot color="#F59E0B" active={!!d.breakfast} />
                      <Dot color="#10B981" active={!!d.lunch} />
                      <Dot color="#6366F1" active={!!d.packed} />
                      <Dot color="#EC4899" active={!!d.dinner} />
                      <Dot color="#8B5CF6" active={!!d.special} />
                    </div>
                    {isHovered && d.note && (
                      <span style={{ fontSize: 11, color: "#999", fontStyle: "italic", marginLeft: 4 }}>{d.note}</span>
                    )}
                  </div>
                </div>
              );
            })}
          </div>
        </Card>
      )}

      {/* Venue */}
      {tab === "venue" && (
        <div style={{ display: "flex", flexDirection: "column", gap: 12 }}>
          {data.venue.map((v, i) => (
            <Card key={i}>
              <h3 style={{ fontSize: 15, fontWeight: 600, margin: "0 0 12px" }}>{v.title}</h3>
              <div style={{ display: "flex", gap: 24, marginBottom: 12 }}>
                <div>
                  <div style={{ fontSize: 10, fontWeight: 600, textTransform: "uppercase", letterSpacing: "0.08em", color: "#bbb", marginBottom: 2 }}>Date</div>
                  <div style={{ fontSize: 14, color: "#555" }}>{v.date}</div>
                </div>
                <div>
                  <div style={{ fontSize: 10, fontWeight: 600, textTransform: "uppercase", letterSpacing: "0.08em", color: "#bbb", marginBottom: 2 }}>Time</div>
                  <div style={{ fontSize: 14, color: "#555" }}>{v.time}</div>
                </div>
                <div>
                  <div style={{ fontSize: 10, fontWeight: 600, textTransform: "uppercase", letterSpacing: "0.08em", color: "#bbb", marginBottom: 2 }}>Guests</div>
                  <div style={{ fontSize: 14, color: "#555" }}>70</div>
                </div>
              </div>
              <p style={{ fontSize: 13, color: "#888", margin: 0, lineHeight: 1.6 }}>{v.details}</p>
            </Card>
          ))}
        </div>
      )}

      {/* Quote Items */}
      {tab === "quote" && (
        <Card>
          <h3 style={{ fontSize: 13, fontWeight: 600, textTransform: "uppercase", letterSpacing: "0.08em", color: "#999", margin: "0 0 20px" }}>Itemised Quote Requested</h3>
          <div style={{ display: "flex", flexDirection: "column", gap: 0 }}>
            {data.quoteItems.map((item, i) => (
              <div key={i} style={{
                display: "flex",
                alignItems: "flex-start",
                gap: 14,
                padding: "12px 0",
                borderBottom: i < data.quoteItems.length - 1 ? "1px solid #f5f5f5" : "none"
              }}>
                <span style={{
                  fontSize: 11,
                  fontWeight: 600,
                  color: "#ccc",
                  minWidth: 20,
                  textAlign: "right",
                  paddingTop: 1
                }}>{i + 1}</span>
                <span style={{ fontSize: 14, color: "#444", lineHeight: 1.5 }}>{item}</span>
              </div>
            ))}
          </div>
        </Card>
      )}

      {/* Footer */}
      <div style={{ marginTop: 48, textAlign: "center" }}>
        <p style={{ fontSize: 11, color: "#ccc", letterSpacing: "0.04em" }}>
          Innovation Academy Ltd · Programme dates: 19 July – 1 August 2026
        </p>
      </div>
    </div>
  );
}
