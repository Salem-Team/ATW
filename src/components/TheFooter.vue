<template>
  <footer>
    <div class="container">
      <div class="top">
        <div class="main_div">
          <div class="title">Join our weekly digest!</div>

          <p>Get exclusive promotions & updates straight to your inbox.</p>
          <div class="add_email">
            <input
              type="email"
              placeholder="Enter Your Email...
        "
            />
            <div>Subscribe</div>
          </div>
          <div class="btn">Create Free Store</div>
        </div>
        <div class="lists">
          <ul>
            <li>FEATURES</li>
            <li>Build Store</li>
            <li>Sell NFT</li>
            <li>Grow Business</li>
          </ul>
          <ul>
            <li>SERVICES</li>
            <li>Concierge</li>
            <li>Customization</li>
          </ul>
          <ul>
            <li>PRODUCT</li>
            <li>About Us</li>
            <li>Whitepaper</li>
            <li>$N1 Token</li>
            <li>Directory</li>
          </ul>
          <ul>
            <li>RESOURCES</li>
            <li>Help Center</li>
            <li>NFTify Branding</li>
            <li>Success Stories</li>
            <li>Video Tutorials</li>
            <li>Contact Support</li>
          </ul>
        </div>
      </div>
    </div>
    <div class="bottom">
      <div class="bottom_container">
        <div>© Copyright NFTify Network. All Rights Reserved.</div>
        <div>
          <div>The Leading No-code NFT Marketplace Solution</div>
          <div class="icons">
            <font-awesome-icon
              :icon="['fab', 'twitter']"
              class="icon twitter"
            />
            <font-awesome-icon
              :icon="['fab', 'telegram']"
              class="icon telegram"
            />
            <font-awesome-icon
              :icon="['fab', 'facebook']"
              class="icon facebook"
            />
            <font-awesome-icon
              :icon="['fab', 'linkedin']"
              class="icon linkedin"
            />
            <font-awesome-icon
              :icon="['fab', 'youtube']"
              class="icon youtube"
            />
            <font-awesome-icon
              :icon="['fab', 'instagram']"
              class="icon instagram"
            />
          </div>
        </div>
        <div>
          <div>Terms of Service</div>
          <div>Privacy Policy</div>
        </div>
      </div>
    </div>
  </footer>
</template>
<style lang="scss" scoped>
footer {
  background: linear-gradient(to top, black, var(--main-color)) !important;
  color: #fff;
  overflow: hidden;
  .container {
    .top {
      padding: 30px 0 30px 0;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 40px;
      .main_div {
        display: flex;
        flex-direction: column;
        gap: 20px;
        .title {
          font-weight: 600;
          font-size: 28px;
          line-height: 100%;
        }
        p {
        }
        .add_email {
          display: flex;
          align-items: center;
          justify-content: start;
          gap: 10px;
          input {
            min-width: 300px;
            font-size: 16px;
            border-radius: 16px;
            background: #000000ab;
            color: #fff;
            padding: 5px 20px;
          }
          div {
            font-size: 16px;
            border-radius: 16px;
            background: black;
            color: #fff;
            padding: 5px 20px;
            cursor: pointer;
            transition: 0.3s;
            &:hover {
              filter: saturate(1.5);
            }
          }
        }
        .btn {
          background: var(--main-color);
          width: fit-content;
          padding: 5px 10px;
          border-radius: 20px;
        }
      }
      .lists {
        display: flex;
        width: 100%;
        justify-content: end;
        gap: 80px;
        ul {
          display: flex;
          flex-direction: column;
          gap: 20px;
          li:first-child {
            font-weight: bold;
          }
          li {
            font-weight: 100;
            color: #d6d5a8;
          }
        }
      }
    }
  }
  .bottom {
    border-top: 4px solid #816797;
    width: 100%;
    padding: 20px 0;
    .bottom_container {
      display: flex;
      align-items: end;
      justify-content: space-between;
      gap: 20px;
      width: 90%;
      margin: 0 auto;
      & > div:first-child {
        font-size: 12px;
      }
      & > div:nth-child(2) {
        font-size: 20px;
        display: flex;
        flex-direction: column;
        gap: 10px;
        align-items: center;
        .icons {
          display: flex;
          gap: 10px;
          align-items: center;
          .icon {
            border: 1px solid #fff;
            border: 1px solid #fff;
            padding: 10px;
            border-radius: 13px;
            font-size: 16px;
            color: #fff;
            transition: 0.3s;
            background: transparent;
            cursor: pointer;
            width: 20px;
            height: 20px;

            &.twitter:hover {
              background-color: #1da1f2;
              color: white;
            }
            &.telegram:hover {
              background-color: #0088cc;
              color: white;
            }
            &.facebook:hover {
              background-color: #3b5998;
              color: white;
            }
            &.linkedin:hover {
              background-color: #0077b5;
              color: white;
            }
            &.youtube:hover {
              background-color: #ff0000;
              color: white;
            }
            &.instagram:hover {
              background: radial-gradient(
                circle at 30% 107%,
                #fdf497 0%,
                #fdf497 5%,
                #fd5949 45%,
                #d6249f 60%,
                #285aeb 90%
              );
              color: white;
            }
          }
        }
      }
      & > div:last-child {
        display: flex;
        align-items: center;
        gap: 10px;
        cursor: pointer;
      }
    }
  }
}

@media (max-width: 1200px) {
  footer .container .top {
    flex-wrap: wrap;
    .lists {
      justify-content: space-between;
      flex-wrap: wrap;
    }
    .add_email {
      flex-direction: column;
      gap: 10px;
      & > div,
      & > input {
        width: 100%;
      }
    }
    .btn {
      width: 100% !important;
    }
  }
  footer .bottom .bottom_container {
    flex-wrap: wrap;
    gap: 10px;
  }
}
</style>
