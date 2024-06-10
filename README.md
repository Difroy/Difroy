- 👋 Hi, I’m @Difroy
- 👀 I’m interested in back-end development
- 🌱 I’m currently learning and delving into technology like Spring/Angular
- 💞️ I’m looking to collaborate with a company that can hire me as an apprentice
- 📫 How to reach me...linkedin profile is available on GItHub
- 😄 Pronouns: ... I'm  Froylan


<% if (plugins.calendar) { %>
  <section>
    <h2 class="field">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" width="16" height="16"><path fill-rule="evenodd" d="M4.75 0a.75.75 0 01.75.75V2h5V.75a.75.75 0 011.5 0V2h1.25c.966 0 1.75.784 1.75 1.75v10.5A1.75 1.75 0 0113.25 16H2.75A1.75 1.75 0 011 14.25V3.75C1 2.784 1.784 2 2.75 2H4V.75A.75.75 0 014.75 0zm0 3.5h8.5a.25.25 0 01.25.25V6h-11V3.75a.25.25 0 01.25-.25h2zm-2.25 4v6.75c0 .138.112.25.25.25h10.5a.25.25 0 00.25-.25V7.5h-11z"></path></svg>
      Contributions calendar
    </h2>
    <div class="row">
      <section>
        <% if (plugins.calendar.error) { %>
          <div class="field error">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" width="16" height="16"><path fill-rule="evenodd" d="M2.343 13.657A8 8 0 1113.657 2.343 8 8 0 012.343 13.657zM6.03 4.97a.75.75 0 00-1.06 1.06L6.94 8 4.97 9.97a.75.75 0 101.06 1.06L8 9.06l1.97 1.97a.75.75 0 101.06-1.06L9.06 8l1.97-1.97a.75.75 0 10-1.06-1.06L8 6.94 6.03 4.97z"></path></svg>
            <%= plugins.calendar.error.message %>
          </div>
        <% } else { %>
          <svg class="calendar" version="1.1" xmlns="http://www.w3.org/2000/svg" viewBox="0,0 795,<%= 130 * plugins.calendar.years.length %>">
            <% for (const [r, {year, weeks}] of Object.entries(plugins.calendar.years)) { %>
              <g transform="translate(0, <%= 14 + r * 130 %>)">
                <text x="0" y="0"><%= year %></text>
                <% for (const [x, week] of Object.entries(weeks)) { %>
                  <g transform="translate(<%= x*15 %>, 0)">
                    <% for (const [y, {color}] of Object.entries(week.contributionDays)) { %>
                      <rect class="day" x="0" y="<%= 4 + (x == 0)*(7-week.contributionDays.length)*15 + y*15 %>" width="11" height="11" fill="<%= color %>" rx="2" ry="2" />
                    <% } %>
                  </g>
                <% } %>
              </g>
            <% } %>
          </svg>
        <% } %>
      </section>
    </div>
  </section>
<% } %>
<!---
Difroy/Difroy is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
