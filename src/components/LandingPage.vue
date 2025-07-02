<template>
  <div class="LandingPage">
    <div class="container">
      <div class="text">Your own NFT Market place without Coding</div>
      <div class="text_2">
        The fastest and easiest way to fully unlock the potential of your
        digital assets. Create and run an exclusive marketplace for your NFT
        business today!
      </div>
      <div class="add_email">
        <input
          type="email"
          placeholder="Enter Your Email...
        "
        />
        <div>start free</div>
      </div>
    </div>
  </div>
  <div class="line">
    <div class="container">
      <div class="feat">
        <div class="logo_text">Powering leading brands</div>
      </div>
      <div class="feat">
        <div class="logo">
          <svg
            width="64"
            height="45"
            viewBox="0 0 64 45"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <ellipse cx="45" cy="10" rx="4" ry="4.5" fill="#D9D9D9" />
            <ellipse cx="32" cy="10" rx="5" ry="4.5" fill="#D9D9D9" />
            <circle cx="19.5" cy="10" r="4.5" fill="#D9D9D9" />
            <ellipse cx="19.5" cy="23" rx="4.5" ry="5.5" fill="#D9D9D9" />
            <circle cx="19.5" cy="36" r="4.5" fill="#D9D9D9" />
            <ellipse cx="32" cy="36" rx="5" ry="4.5" fill="#D9D9D9" />
            <ellipse cx="31.5" cy="22.5" rx="1.5" ry="1" fill="#D9D9D9" />
            <circle cx="44.5" cy="23" r="1.5" fill="#D9D9D9" />
            <circle cx="44.5" cy="35" r="1.5" fill="#D9D9D9" />
            <path
              d="M34 13.5C37.2436 10.7699 39.2188 10.8223 43 13.5V6.5C39.4856 7.85863 37.5145 7.88516 34 6.5V13.5Z"
              fill="#D9D9D9"
            />
            <path
              d="M22 14.5C25.2436 11.3798 27.2188 11.4398 31 14.5V6.5C27.4856 8.05272 25.5145 8.08304 22 6.5V14.5Z"
              fill="#D9D9D9"
            />
            <path
              d="M22 39.5C25.2436 36.3798 27.2188 36.4398 31 39.5V31.5C27.4856 33.0527 25.5145 33.083 22 31.5V39.5Z"
              fill="#D9D9D9"
            />
            <path
              d="M16.2116 12.0289C18.8601 15.5136 18.8035 17.6313 16.1864 21.6787L23.0004 21.6965C21.6877 17.9249 21.6674 15.8114 23.0257 12.0467L16.2116 12.0289Z"
              fill="#D9D9D9"
            />
            <path
              d="M16.2116 24.5845C18.8601 28.0692 18.8035 30.1869 16.1864 34.2343L23.0004 34.2521C21.6877 30.4805 21.6674 28.367 23.0257 24.6023L16.2116 24.5845Z"
              fill="#D9D9D9"
            />
          </svg>
        </div>
        <div class="logo_text">Coindesk</div>
      </div>
      <div class="feat">
        <div class="logo">
          <svg
            width="64"
            height="45"
            viewBox="0 0 64 45"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <rect x="13" y="8" width="16" height="12" fill="#D9D9D9" />
            <rect x="13" y="26" width="16" height="11" fill="#D9D9D9" />
            <path
              fill-rule="evenodd"
              clip-rule="evenodd"
              d="M49.2318 8H34.7646V29.3609L49.2318 8ZM36.6821 37H51.2193V15.5356L36.6821 37Z"
              fill="#D9D9D9"
            />
          </svg>
        </div>
        <div class="logo_text">H E F T Y V E R S E</div>
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
.LandingPage {
  background-attachment: fixed;
  background-image: url("../assets/queen.jpg");
  height: 95vh;
  background-position: top;
  background-repeat: no-repeat;
  background-size: cover;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
  &::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: inherit;
    filter: brightness(0.5);
    z-index: 0;
  }
  .container {
    z-index: 1;

    .text {
      font-family: monospace;
      font-weight: 700;
      font-size: 48px;
      line-height: 1.5;
      letter-spacing: 0%;
      text-align: center;
      max-width: 673px;
      text-align: center;
      margin: 0 auto 36px;
      color: #fff;
    }
    .text_2 {
      font-family: monospace;
      font-weight: 400;
      font-size: 18px;
      line-height: 1.5;
      letter-spacing: 0%;
      text-align: center;
      max-width: 594px;
      text-align: center;
      margin: 0 auto;
      color: #fff;
    }
    .add_email {
      display: flex;
      align-items: center;
      justify-content: center;
      margin-top: 36px;
      gap: 10px;
      input {
        min-width: 300px;
        font-size: 20px;
        border-radius: 16px;
        background: #000000ab;
        color: #fff;
        padding: 5px 10px;
      }
      div {
        font-size: 20px;
        border-radius: 16px;
        background: var(--main-color);
        color: #fff;
        padding: 5px 10px;
        cursor: pointer;
        transition: 0.3s;
        &:hover {
          filter: saturate(1.5);
        }
      }
    }
  }
}
//Start  line
.line {
  position: relative;
  background: hsl(272, 19%, 50%);
  .container {
    padding: 20px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    .feat {
      display: flex;
      align-items: center;
      justify-content: center;
      .logo_text {
        color: #fff;
        font-size: 25px;
      }
      .logo_text:first-child {
        color: #fff;
        font-size: 35px;
      }
    }
  }
}
//End  line

@media (max-width: 720px) {
  .add_email {
    flex-direction: column;
    gap: 10px;
    & > div,
    & > input {
      width: 100%;
    }
  }

  .line {
    .container {
      overflow: auto;
      .feat {
        min-width: 226px;
        .logo_text {
          font-size: 20px !important;
        }
      }
    }
  }
}

// Animation
@keyframes fadeUp {
  0% {
    opacity: 0;
    transform: translateY(30px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.text,
.text_2,
.add_email,
.line .feat {
  opacity: 0;
  animation: fadeUp 1s ease-out forwards;
}

.text {
  animation-delay: 0.3s;
}
.text_2 {
  animation-delay: 0.6s;
}
.add_email {
  animation-delay: 0.9s;
}
.line .feat:nth-child(1) {
  animation-delay: 1.2s;
}
.line .feat:nth-child(2) {
  animation-delay: 1.4s;
}
.line .feat:nth-child(3) {
  animation-delay: 1.6s;
}
</style>
