<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>MentorAI - Mentorship Intelligence</title>

<style>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: Arial, Helvetica, sans-serif;
    background: #f5f7fb;
    color: #172033;
}

.app {
    display: flex;
    min-height: 100vh;
}

/* ================= SIDEBAR ================= */

.side {
    width: 235px;
    background: #111827;
    color: white;
    padding: 24px 16px;
}

.brand {
    font-size: 20px;
    font-weight: 800;
    margin-bottom: 28px;
}

.brand span {
    display: block;
    font-size: 12px;
    color: #9ca3af;
    margin-top: 4px;
}

.nav {
    padding: 12px 14px;
    border-radius: 10px;
    margin: 6px 0;
    color: #cbd5e1;
    cursor: pointer;
}

.nav.active,
.nav:hover {
    background: #253047;
    color: white;
}

/* ================= MAIN ================= */

.main {
    flex: 1;
    padding: 28px;
    overflow: auto;
}

.top {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 24px;
}

.top h1 {
    margin: 0;
    font-size: 25px;
}

.mentor {
    background: white;
    border: 1px solid #e5e7eb;
    padding: 10px 14px;
    border-radius: 10px;
    font-size: 13px;
}

/* ================= DASHBOARD CARDS ================= */

.cards {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 14px;
}

.card {
    background: white;
    border: 1px solid #e5e7eb;
    border-radius: 14px;
    padding: 18px;
}

.label {
    font-size: 12px;
    color: #64748b;
}

.value {
    font-size: 28px;
    font-weight: 800;
    margin-top: 7px;
}

.danger {
    color: #dc2626;
}

.warn {
    color: #d97706;
}

.good {
    color: #16a34a;
}

/* ================= GRID ================= */

.grid {
    display: grid;
    grid-template-columns: 1.35fr 1fr;
    gap: 18px;
    margin-top: 18px;
}

.panel {
    background: white;
    border: 1px solid #e5e7eb;
    border-radius: 14px;
    padding: 18px;
}

.panel h2 {
    font-size: 17px;
    margin: 0 0 14px;
}

/* ================= STUDENTS ================= */

.student {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 13px 0;
    border-bottom: 1px solid #eef2f7;
}

.student:last-child {
    border-bottom: 0;
}

.name {
    font-weight: 700;
}

.meta {
    font-size: 12px;
    color: #64748b;
    margin-top: 4px;
}

.badge {
    padding: 5px 9px;
    border-radius: 999px;
    font-size: 11px;
    font-weight: 700;
}

.red {
    background: #fee2e2;
    color: #b91c1c;
}

.yellow {
    background: #fef3c7;
    color: #92400e;
}

.green {
    background: #dcfce7;
    color: #166534;
}

/* ================= BARS ================= */

.riskrow {
    margin: 14px 0;
}

.riskhead {
    display: flex;
    justify-content: space-between;
    font-size: 13px;
}

.bar {
    height: 8px;
    background: #e5e7eb;
    border-radius: 99px;
    margin-top: 8px;
    overflow: hidden;
}

.fill {
    height: 100%;
    border-radius: 99px;
}

/* ================= AI ASSISTANT ================= */

.assistant {
    display: flex;
    flex-direction: column;
    height: 390px;
}

.messages {
    flex: 1;
    overflow: auto;
    padding-right: 4px;
}

.msg {
    max-width: 88%;
    padding: 11px 13px;
    border-radius: 12px;
    margin: 9px 0;
    font-size: 13px;
    line-height: 1.45;
}

.ai {
    background: #f1f5f9;
}

.me {
    background: #e0e7ff;
    margin-left: auto;
}

.chips {
    display: flex;
    gap: 7px;
    flex-wrap: wrap;
    margin: 10px 0;
}

.chip {
    border: 1px solid #dbe2ea;
    background: white;
    border-radius: 20px;
    padding: 7px 10px;
    font-size: 11px;
    cursor: pointer;
}

.input {
    display: flex;
    gap: 8px;
    border-top: 1px solid #e5e7eb;
    padding-top: 12px;
}

.input input {
    flex: 1;
    padding: 11px;
    border: 1px solid #d1d5db;
    border-radius: 9px;
}

.input button {
    background: #111827;
    color: white;
    border: 0;
    border-radius: 9px;
    padding: 0 16px;
    cursor: pointer;
}

/* ================= BRIEFING ================= */

.brief {
    background: #f8fafc;
    border-radius: 10px;
    padding: 12px;
    margin-top: 10px;
    font-size: 12px;
    line-height: 1.55;
}

.action {
    margin-top: 8px;
    padding: 9px;
    background: white;
    border: 1px solid #e5e7eb;
    border-radius: 8px;
}

.footer {
    font-size: 11px;
    color: #64748b;
    margin-top: 18px;
}

/* ================= RESPONSIVE ================= */

@media(max-width:900px) {

    .side {
        width: 70px;
    }

    .brand span,
    .nav span {
        display: none;
    }

    .cards {
        grid-template-columns: repeat(2, 1fr);
    }

    .grid {
        grid-template-columns: 1fr;
    }
}

@media(max-width:560px) {

    .side {
        display: none;
    }

    .main {
        padding: 16px;
    }

    .cards {
        grid-template-columns: 1fr;
    }
}
</style>
</head>


<body>

<div class="app">

<!-- ================= SIDEBAR ================= -->

<aside class="side">

    <div class="brand">
        MentorAI
        <span>Mentorship Intelligence</span>
    </div>

    <div class="nav active">
        ▣ <span>Dashboard</span>
    </div>

    <div class="nav">
        ⚠ <span>Risk & Growth</span>
    </div>

    <div class="nav">
        ✦ <span>AI Assistant</span>
    </div>

    <div class="nav">
        ◷ <span>Meetings</span>
    </div>

    <div class="nav">
        ◎ <span>Students</span>
    </div>

</aside>


<!-- ================= MAIN CONTENT ================= -->

<main class="main">

    <div class="top">

        <div>
            <h1>AI Mentor Dashboard</h1>

            <div class="label">
                Early intervention + intelligent mentorship support
            </div>
        </div>

        <div class="mentor">
            👩‍🏫 Mentor: Dr. Priya · CSE-A
        </div>

    </div>


    <!-- ================= DASHBOARD CARDS ================= -->

    <section class="cards">

        <div class="card">
            <div class="label">
                My Mentees
            </div>

            <div class="value">
                42
            </div>
        </div>


        <div class="card">

            <div class="label">
                Need Attention
            </div>

            <div class="value danger">
                5
            </div>

        </div>


        <div class="card">

            <div class="label">
                Improving
            </div>

            <div class="value good">
                18
            </div>

        </div>


        <div class="card">

            <div class="label">
                Pending Actions
            </div>

            <div class="value warn">
                7
            </div>

        </div>

    </section>



    <!-- ================= MAIN GRID ================= -->

    <section class="grid">


        <!-- AI RISK PANEL -->

        <div class="panel">

            <h2>
                🧠 AI Risk & Growth Prediction
            </h2>


            <!-- Student A -->

            <div class="student">

                <div>

                    <div class="name">
                        Student A
                    </div>

                    <div class="meta">
                        Academic trend ↓ · Attendance 68%
                    </div>

                </div>

                <div>
                    <span class="badge red">
                        High Risk · 82%
                    </span>
                </div>

            </div>


            <!-- Student B -->

            <div class="student">

                <div>

                    <div class="name">
                        Student B
                    </div>

                    <div class="meta">
                        Low engagement · Goal inactive
                    </div>

                </div>

                <div>
                    <span class="badge yellow">
                        Medium · 61%
                    </span>
                </div>

            </div>


            <!-- Student C -->

            <div class="student">

                <div>

                    <div class="name">
                        Student C
                    </div>

                    <div class="meta">
                        Strong scores · Skills improving
                    </div>

                </div>

                <div>
                    <span class="badge green">
                        Growth · 89%
                    </span>
                </div>

            </div>


            <!-- Risk Bars -->

            <div class="riskrow">

                <div class="riskhead">

                    <span>
                        Academic performance
                    </span>

                    <b>
                        82%
                    </b>

                </div>

                <div class="bar">

                    <div
                        class="fill"
                        style="width:82%;background:#dc2626">
                    </div>

                </div>

            </div>


            <div class="riskrow">

                <div class="riskhead">

                    <span>
                        Mentorship engagement
                    </span>

                    <b>
                        54%
                    </b>

                </div>

                <div class="bar">

                    <div
                        class="fill"
                        style="width:54%;background:#d97706">
                    </div>

                </div>

            </div>


            <div class="riskrow">

                <div class="riskhead">

                    <span>
                        Skill growth
                    </span>

                    <b>
                        76%
                    </b>

                </div>

                <div class="bar">

                    <div
                        class="fill"
                        style="width:76%;background:#16a34a">
                    </div>

                </div>

            </div>

        </div>



        <!-- ================= AI ASSISTANT ================= -->

        <div class="panel assistant">

            <h2>
                🤖 AI Mentor Assistant
            </h2>


            <div class="messages" id="messages">


                <div class="msg ai">

                    <b>
                        AI Assistant
                    </b>

                    <br>

                    Good morning. You have 5 mentees
                    needing attention. I can prepare
                    student briefings, identify risk
                    factors, summarize meetings, or
                    suggest follow-up actions.

                </div>



                <div class="msg ai">

                    <b>
                        Next meeting: Student A
                    </b>

                    <div class="brief">

                        Performance has declined recently.

                        Previous action:
                        Complete DBMS practice set.

                        Suggested focus:
                        Understand the reason for the
                        decline and create a short
                        recovery plan.

                    </div>

                </div>


            </div>



            <!-- QUICK QUESTIONS -->

            <div class="chips">

                <button
                    class="chip"
                    onclick="ask('Which students need immediate attention?')">

                    Who needs attention?

                </button>


                <button
                    class="chip"
                    onclick="ask('Prepare an agenda for Student A')">

                    Prepare Student A agenda

                </button>


                <button
                    class="chip"
                    onclick="ask('Show pending actions')">

                    Pending actions

                </button>

            </div>



            <!-- CHAT INPUT -->

            <div class="input">

                <input
                    id="q"
                    placeholder="Ask about your authorized mentee data..."
                    onkeydown="if(event.key==='Enter')send()"
                >

                <button onclick="send()">
                    Ask
                </button>

            </div>

        </div>

    </section>



    <!-- ================= MEETING BRIEF ================= -->

    <div class="panel" style="margin-top:18px">

        <h2>
            📋 Next Meeting Briefing — Student A
        </h2>


        <div class="brief">

            <b>Context:</b>

            Recent academic performance is
            trending downward; attendance is
            below the department target.

            <br><br>

            <b>Previous concern:</b>

            Difficulty with DBMS concepts.

            <br><br>

            <b>Pending action:</b>

            Complete 3 SQL practice exercises.

            <br><br>

            <b>Suggested questions:</b>

            "What is blocking your progress?"

            ·

            "Do you need additional academic support?"

            <br><br>

            <b>Recommended intervention:</b>

            Set a one-week study goal and schedule
            a follow-up.

        </div>


        <div class="footer">

            Prototype uses sample data only.
            In production, role-based access control
            ensures the AI only retrieves data the
            mentor is authorized to view.

        </div>

    </div>


</main>

</div>



<!-- ================= JAVASCRIPT ================= -->

<script>


/*
    Add a message to the AI chat
*/

function add(text, cls) {

    const messages =
        document.getElementById("messages");

    const div =
        document.createElement("div");

    div.className = "msg " + cls;

    div.innerHTML = text;

    messages.appendChild(div);

    messages.scrollTop =
        messages.scrollHeight;
}



/*
    Put a suggested question
    into the chat box
*/

function ask(question) {

    document.getElementById("q").value =
        question;

    send();
}



/*
    Send question to AI

    NOTE:
    This prototype uses predefined
    responses.

    In the real application,
    this function will call:

    Frontend
       ↓
    FastAPI
       ↓
    Authorization
       ↓
    Database
       ↓
    AI / LLM
       ↓
    Response
*/

function send() {

    const input =
        document.getElementById("q");

    const text =
        input.value.trim();


    if (!text)
        return;


    /*
        Display mentor message
    */

    add(text, "me");

    input.value = "";


    /*
        Simulated AI response
    */

    setTimeout(function() {


        let answer =

        `
        I found 3 students requiring
        attention:

        Student A — declining academic trend

        Student B — low engagement

        Student D — overdue mentorship action.

        I can show the supporting factors
        and recommended interventions.
        `;


        /*
            Meeting agenda
        */

        if (
            text
            .toLowerCase()
            .includes("agenda")
        ) {

            answer = `

            <b>
                Suggested agenda for Student A
            </b>

            <br><br>

            1. Review recent performance

            <br>

            2. Discuss DBMS difficulty

            <br>

            3. Review pending SQL exercises

            <br>

            4. Agree on a one-week goal

            <br>

            5. Schedule follow-up

            `;

        }


        /*
            Pending actions
        */

        if (
            text
            .toLowerCase()
            .includes("pending")
        ) {

            answer = `

            <b>
                Pending actions
            </b>

            <br><br>

            • Student A —
            DBMS practice set

            <br>

            • Student B —
            Career roadmap update

            <br>

            • Student D —
            Follow-up meeting

            <br><br>

            I can prioritize these
            by urgency.

            `;

        }


        /*
            Display AI response
        */

        add(answer, "ai");


    }, 400);

}

</script>

</body>
</html>
