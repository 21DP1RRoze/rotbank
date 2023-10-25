<template>
  <div class="firsthead">
    <div class="topbuffer">
        <ul>
        <li class="dpac"><a href="#depositID"><i class="fa-solid fa-file-invoice-dollar"></i> Deposit Account</a></li>
        <li class="loan"><a href="#loanID"><i class="fa-solid fa-landmark"></i> Loans</a></li>
        <li class="crdcd"><a href="#creditID"><i class="fa-solid fa-credit-card"></i> Credit Cards</a></li>
        <li class="insur"><a href="#insureID"><i class="fa-solid fa-car-burst"></i> Insurance</a></li>
        <li class="atm"><a href="#atmID"><i class="fa-solid fa-money-bills"></i> ATMs</a></li>
        <li class="pens"><a href="#pensID"><i class="fa-solid fa-person-cane"></i> Pensions</a></li>
        </ul>
    </div>
    <div class="maincontent">
        <div class="div1"><img src="../assets/logo.png" alt="logo" width="400px"></div> <!--logo-->
        <div class="div2"></div> <!--seperator-->
        <div class="div3">Reliability</div>
        <div class="div4">Trust</div>
        <div class="div5">Security</div>
        <div class="div6">mm</div>
        <div class="div7">dsdf</div>
        <div class="div8">zzz</div>
    </div>
    <div id="depositID">
        <div class="depositContainer">
            <div class="depositIMG">Deposit account.</div>
            <div class="depositDIVd"></div>
            <div class="depositTEXT1">At [Bank Name], we're dedicated to helping you secure your financial future. Our Deposit Account Service is designed to provide you with a safe and dependable way to save and manage your money.

Here's what you can expect:

Security and Peace of Mind: Your funds are protected with the highest level of security and compliance measures, ensuring your peace of mind.

Competitive Returns: Your money will grow with our competitive interest rates, helping you reach your financial goals faster.

Convenience and Accessibility: Manage your account with ease through our online platform or mobile app, or visit one of our branches. Your finances are at your fingertips 24/7.

Tailored Solutions: Choose from a range of deposit account options, including regular savings accounts and certificates of deposit, to find the perfect fit for your savings goals.

Transparent Banking: We believe in straightforward banking with no monthly maintenance fees, so you can keep more of your savings.

Automated Savings: Set up automatic transfers to make saving effortless and consistent, allowing you to stay on track.

Overdraft Protection: Opt for our optional overdraft protection to shield yourself from unexpected expenses and costly fees.

Expert Guidance: Our experienced bankers are here to assist you in selecting the right deposit account, understanding your financial aspirations, and providing personalized advice.

Digital Tools: Access an array of digital tools to track your savings progress, set goals, and plan for your financial future.

Community Commitment: [Bank Name] actively supports local initiatives and charitable organizations, making your savings count beyond your personal goals.

Whether you're a seasoned saver or just starting on your journey to financial independence, our Deposit Account Service is the ideal choice. With our focus on security, convenience, and your satisfaction, you can trust us to help you build a brighter financial future.

Open a deposit account with us today and take the first step toward realizing your financial dreams. Your future starts here at [Bank Name]</div>
        </div>
    </div>
    <div id="loanID"></div>
    <div id="creditID"></div>
    <div id="insureID"></div>
    <div id="atmID"></div>
    <div id="pensID"></div>
</div>
</template>

<script>
export default {

}
</script>

<style>
.topbuffer {
    height:75px;
    font-size: 18pt;
    text-align:center;
    font-family: 'Urbanist', sans-serif;
    padding-top: 22px;
    color:#2B2D42;
    user-select: none;
}
.topbuffer ul {
    padding:0;
}
.topbuffer li {
    display:inline;

}
.topbuffer li::after {
  content: " "; /* seperators */
  word-spacing: 3em;
  background-image: linear-gradient(
    90deg,
    transparent 0 calc(50% - 0.03em),
    currentcolor 0 calc(50% + 0.03em),
    transparent 0
  );
}

.topbuffer a:hover {
    position:relative;
    top: -5px;
}

    .maincontent {
    display: grid;
    grid-template-columns: 400px 50px 250px 250px 250px;
    grid-template-rows: 100px 100px 100px 100px;
    grid-column-gap: 0px;
    grid-row-gap: 0px;
    height: 35vh;
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    padding-left: 10%;
    padding-right: 10%;
    padding-top: 20px;
    border: 3px red solid;

    } 
    .div1 { grid-area: 1 / 1 / 3 / 3; }
    .div2 { grid-area: 1 / 3 / 3 / 4; }
    .div3 { grid-area: 1 / 4 / 2 / 5; }
    .div4 { grid-area: 1 / 5 / 2 / 6; }
    .div5 { grid-area: 1 / 6 / 2 / 7; }
    .div6 { grid-area: 2 / 4 / 3 / 5; }
    .div7 { grid-area: 2 / 5 / 3 / 6; }
    .div8 { grid-area: 2 / 6 / 3 / 7; } 

    .div1 {
        position: relative;
        top: 25%;
    }
    .div2 {
        height: 100%;
        width: 0.5px;
        background-color: #2B2D42;
        position:relative;
        left: 32px;
    }
    .div3, .div4, .div5, .div6, .div7, .div8{
        width: 230px;
        height: 75px;
        background-color: rgba(229, 56, 59,.95); 
        position:relative;
        right: 130px;
        top: 10%;
        font-size: 40pt;
        text-align: center;
        padding-top: 6px;
        color:#2B2D42;
        font-family: 'Bebas Neue', sans-serif;
        transition:ease-in-out 200ms;
        user-select: none;  
    }

    .div3:hover, .div4:hover, .div5:hover, .div6:hover, .div7:hover, .div8:hover {
        background-color: #2B2D42;
        cursor:default;
        color: rgba(229, 56, 59,.95);
    }
    .depositContainer {
        position:relative;
        top: 50px;
        display: grid;
        grid-template-columns: 25vw, 10px, 100vw;
        grid-template-rows: 5fr repeat(4, 1fr);
        grid-column-gap: 0px;
        grid-row-gap: 0px; 
        border: 3px red solid;
    }
    .depositIMG { grid-area: 1 / 1 / 2 / 2; }
    .depositDIVd { grid-area: 1 / 2 / 2 / 3; }
    .depositTEXT1 { grid-area: 1 / 3 / 2 / 3; }

    .depositIMG {
        background-image: linear-gradient(125deg, rgba(22, 26, 29, 0.2), rgba(102, 7, 8, 0.9)), url('../assets/bankbuilding.jpg');
        height: 50vh;
        width: 25vw;
        background-position: center;
        background-repeat: none;
        background-size: cover;
        position:relative;
        top: 5%;
        margin-right: 39px;
        font-size: 90pt;
        font-family: 'Koulen', sans-serif;
        color: white;
        line-height: 100px;
        padding-top: 27%;
        padding-left: 10px;
        user-select: none;  

    }

    .depositDIVd {
        height: 55vh;
        background-color: #2B2D42;
        width: 1px;
        position:relative;
        right: 100%;
        
    }

    .depositTEXT1 {
        width: 800px;
        position:relative;
        column-count: 2;
        right: 25%;
    }
</style>