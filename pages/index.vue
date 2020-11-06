<template>
  <div class="container">
    <c-mouse />
    <section class="c-section c-hero">
      <div class="c-hero__text-wrap">
        <h1 class="c-section__heading">Adetomiwa Isiaka</h1>
        <p class="c-section__subtext">
          I’m a content developer currently working in Lagos, Nigeria.
          Presently, I work as a content strategist, copy writer, content writer
          and marketer at
          <a
            href="https://gomoney.global/"
            target="_blank"
            class="c-link c-link--green c-link--underline"
            >gomoney</a
          >, and a curator at
          <a
            href="https://thatnewnews.substack.com/"
            target="_blank"
            class="c-link c-link--red c-link--underline"
            >That New News</a
          >. I’m also a contributor at
          <a
            href="https://globalvoices.org/author/adetomiwa-isiaka/"
            class="c-link c-link--green c-link--underline"
            >Global Voices</a
          >
          and a sometimes <span class="c-hero__text-yogi">yogi</span>.
        </p>
        <div class="c-hero__scroll">
          <svg
            viewBox="0 0 120 120"
            fill="transparent"
            class="c-hero__scroll-circle"
          >
            <circle
              cx="60"
              cy="60"
              r="59.5"
              stroke="black"
              stroke-width="0.7"
            />
          </svg>
          <svg
            x="0px"
            y="0px"
            viewBox="0 0 512 512"
            class="c-hero__scroll-arrow"
          >
            <g>
              <g>
                <path
                  d="M455.543,301.781c-4.16-4.16-10.923-4.16-15.083,0L266.657,475.584V10.667C266.657,4.779,261.879,0,255.991,0
			c-5.888,0-10.667,4.779-10.667,10.667v464.917L71.543,301.803c-4.16-4.16-10.923-4.16-15.083,0c-4.16,4.16-4.16,10.923,0,15.083
			l191.979,191.979c0.981,0.981,2.176,1.771,3.477,2.325c1.301,0.533,2.688,0.811,4.075,0.811c1.387,0,2.773-0.277,4.075-0.811
			c1.323-0.533,2.496-1.323,3.477-2.325l191.979-191.979C459.703,312.704,459.703,305.963,455.543,301.781z"
                />
              </g>
            </g>
          </svg>
        </div>
      </div>
      <div class="c-hero__image">
        <div class="c-hero__image-overlay" />
        <img
          id="js-hero-img"
          src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wCEAAEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAf/AABEIAA4ACgMBEQACEQEDEQH/xAGiAAABBQEBAQEBAQAAAAAAAAAAAQIDBAUGBwgJCgsQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+gEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoLEQACAQIEBAMEBwUEBAABAncAAQIDEQQFITEGEkFRB2FxEyIygQgUQpGhscEJIzNS8BVictEKFiQ04SXxFxgZGiYnKCkqNTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqCg4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2dri4+Tl5ufo6ery8/T19vf4+fr/2gAMAwEAAhEDEQA/APsT9tT9s39rjwD4z8Sa5+zfp2mj4IeBPgt8WPGHizxV4m8J6P4i0vWfiBJrPinTvCOiafbR3cmvSancI3htvD2mFdLttb+06vLHb64tjcLpv5vTw+BrQl7eDnTxGNwuHcnNwUIVMRTU5b2Sd5WlJ2Tj30f2NB1KkpV4YyVN4ahi6kMMqKm6840qkoXlJXUYRSbUbKyabu1f6i+Avxl8C+OPgZ8GPGvxE8QeA7H4geL/AIT/AA68UeOrL7LY6R9j8Y+IPCGj6t4ntf7KllMumfZ9bu76L+z5SZLLZ9mclojXh4qjQpYrE0qUU6VLEVqdN25r04VJRg+ZK0rxS1Wj3O2lOpOlTnPn5pU4Sl7sl70opvS2mrP5c/j3+3T4k0DxjceFP7b+IOh/D+9+G/hCG+8L+DrzSdKuvE9zYat4hBOr687G60vT7PU7Nrm2sLe31iO/aKGe5Nokz2EH2+XZb9YoLncZU415xqw5uRzScKluZ06is3y7RjJPmtJ6M8Gtj4YD2fJSVSu6SlCpVj7SnSupRXLR54RlLR3dRzjayVPdv7/8M/FP9oGfw34fmt/F2itbzaHpMsBurHRftJhksLd4jceV4M8rzyhUy+X+78zds+XFTKjkilJPJ4NqTTf1rEK7T1dk0tX2SXkc3tcweqzCaT1S+rUdPLc//9k="
          data-src="https://res.cloudinary.com/daitiebum/image/upload/v1604398570/tomiwa-website/tomiwa-min.jpg"
          class="lazyload"
          alt="tomiwa's picture"
        />
      </div>
    </section>
    <p class="c-section-no">002</p>
    <section ref="skillsetSection" class="c-section c-skillset">
      <h1 class="c-section__heading">What I do</h1>
      <p class="c-section__subtext">
        My goal is to help you craft the best formats and mediums to talk to
        your users with a productive mix of all my skillsets.
      </p>
      <div class="c-skillset__skill c-skillset__skill--first">
        <svg
          width="1400"
          height="158"
          viewBox="0 0 160 180"
          fill="none"
          class="c-skillset__skill-icon"
        >
          <path
            d="M82.4242 19.5151V4.84848H89.6969C90.3399 4.84848 90.9565 4.59307 91.4111 4.13844C91.8658 3.6838 92.1212 3.06719 92.1212 2.42424C92.1212 1.78129 91.8658 1.16468 91.4111 0.710044C90.9565 0.255411 90.3399 0 89.6969 0H70.303C69.66 0 69.0434 0.255411 68.5888 0.710044C68.1342 1.16468 67.8788 1.78129 67.8788 2.42424C67.8788 3.06719 68.1342 3.6838 68.5888 4.13844C69.0434 4.59307 69.66 4.84848 70.303 4.84848H77.5757V19.5151C56.578 20.1517 36.6733 29.022 22.1603 44.2102C7.64736 59.3984 -0.309133 79.6857 0.00919679 100.691C0.327526 121.696 8.89514 141.732 23.8617 156.474C38.8282 171.215 58.9926 179.478 80 179.478C101.007 179.478 121.172 171.215 136.138 156.474C151.105 141.732 159.672 121.696 159.991 100.691C160.309 79.6857 152.353 59.3984 137.84 44.2102C123.327 29.022 103.422 20.1517 82.4242 19.5151V19.5151ZM80 174.545C65.1364 174.545 50.6066 170.138 38.248 161.88C25.8894 153.622 16.2571 141.885 10.5691 128.153C4.88102 114.421 3.39277 99.3105 6.29251 84.7326C9.19224 70.1546 16.3497 56.7639 26.8598 46.2538C37.37 35.7436 50.7607 28.5862 65.3386 25.6864C79.9166 22.7867 95.027 24.2749 108.759 29.963C122.491 35.651 134.228 45.2834 142.486 57.642C150.744 70.0006 155.151 84.5303 155.151 99.3939C155.151 119.325 147.234 138.44 133.14 152.534C119.046 166.628 99.9314 174.545 80 174.545V174.545Z"
            fill="#0093A9"
            fill-opacity="0.4"
          />
          <path
            d="M12.1212 33.9393C14.5185 33.9393 16.8621 33.2284 18.8554 31.8965C20.8487 30.5646 22.4023 28.6716 23.3197 26.4567C24.2372 24.2418 24.4772 21.8047 24.0095 19.4534C23.5418 17.1021 22.3874 14.9423 20.6922 13.2471C18.997 11.5519 16.8372 10.3975 14.4859 9.92981C12.1346 9.46211 9.69748 9.70215 7.48262 10.6196C5.26776 11.537 3.37469 13.0906 2.04279 15.0839C0.710897 17.0773 0 19.4208 0 21.8181C0 25.0329 1.27705 28.1159 3.55022 30.3891C5.82338 32.6623 8.90646 33.9393 12.1212 33.9393ZM12.1212 14.5454C13.5596 14.5454 14.9657 14.9719 16.1617 15.7711C17.3577 16.5702 18.2899 17.706 18.8403 19.035C19.3908 20.3639 19.5348 21.8262 19.2542 23.237C18.9736 24.6477 18.2809 25.9436 17.2638 26.9607C16.2467 27.9778 14.9508 28.6705 13.54 28.9511C12.1293 29.2317 10.667 29.0877 9.33805 28.5372C8.00914 27.9868 6.87329 27.0546 6.07415 25.8586C5.27502 24.6626 4.84848 23.2565 4.84848 21.8181C4.84848 19.8893 5.61471 18.0394 6.97861 16.6755C8.34251 15.3116 10.1924 14.5454 12.1212 14.5454Z"
            fill="#0093A9"
            fill-opacity="0.4"
          />
          <path
            d="M147.879 33.9393C150.276 33.9393 152.62 33.2284 154.613 31.8965C156.606 30.5646 158.16 28.6716 159.077 26.4567C159.995 24.2418 160.235 21.8047 159.767 19.4534C159.299 17.1021 158.145 14.9423 156.45 13.2471C154.755 11.5519 152.595 10.3975 150.244 9.92981C147.892 9.46211 145.455 9.70215 143.24 10.6196C141.025 11.537 139.132 13.0906 137.8 15.0839C136.468 17.0773 135.758 19.4208 135.758 21.8181C135.758 25.0329 137.035 28.1159 139.308 30.3891C141.581 32.6623 144.664 33.9393 147.879 33.9393ZM147.879 14.5454C149.317 14.5454 150.723 14.9719 151.919 15.7711C153.115 16.5702 154.047 17.706 154.598 19.035C155.148 20.3639 155.292 21.8262 155.012 23.237C154.731 24.6477 154.038 25.9436 153.021 26.9607C152.004 27.9778 150.708 28.6705 149.298 28.9511C147.887 29.2317 146.425 29.0877 145.096 28.5372C143.767 27.9868 142.631 27.0546 141.832 25.8586C141.033 24.6626 140.606 23.2565 140.606 21.8181C140.606 19.8893 141.372 18.0394 142.736 16.6755C144.1 15.3116 145.95 14.5454 147.879 14.5454V14.5454Z"
            fill="#0093A9"
            fill-opacity="0.4"
          />
          <path
            d="M79.9999 48.4847C68.1816 48.5576 56.7567 52.7402 47.6848 60.315C45.7825 58.9857 43.5319 58.2439 41.2121 58.1817C38.776 58.2208 36.4083 58.9931 34.4176 60.3978C32.427 61.8026 30.9059 63.7746 30.0527 66.0567C29.1996 68.3388 29.0539 70.8251 29.6348 73.1912C30.2156 75.5573 31.4961 77.6935 33.309 79.3211C30.5184 85.6446 29.0816 92.4819 29.0909 99.3938C29.0909 109.463 32.0766 119.305 37.6706 127.677C43.2645 136.049 51.2155 142.574 60.5179 146.428C69.8203 150.281 80.0564 151.289 89.9318 149.325C99.8072 147.36 108.878 142.512 115.998 135.392C123.118 128.272 127.966 119.201 129.931 109.326C131.895 99.4503 130.887 89.2142 127.034 79.9118C123.181 70.6093 116.655 62.6584 108.283 57.0645C99.9115 51.4705 90.0688 48.4847 79.9999 48.4847ZM41.2121 63.0302C42.6505 63.0302 44.0566 63.4567 45.2526 64.2559C46.4486 65.055 47.3807 66.1908 47.9312 67.5198C48.4816 68.8487 48.6257 70.311 48.345 71.7217C48.0644 73.1325 47.3718 74.4284 46.3547 75.4455C45.3375 76.4626 44.0417 77.1553 42.6309 77.4359C41.2201 77.7165 39.7578 77.5725 38.4289 77.022C37.1 76.4716 35.9642 75.5394 35.165 74.3434C34.3659 73.1474 33.9393 71.7413 33.9393 70.3029C33.9393 68.3741 34.7056 66.5242 36.0695 65.1603C37.4334 63.7964 39.2832 63.0302 41.2121 63.0302ZM79.9999 145.454C67.7839 145.454 56.0682 140.602 47.4302 131.964C38.7921 123.326 33.9393 111.61 33.9393 99.3938C33.922 93.3076 35.1599 87.2831 37.5757 81.6968C39.3783 82.3688 41.3189 82.5852 43.2252 82.327C45.1316 82.0688 46.9447 81.3439 48.5036 80.2167C50.0625 79.0895 51.319 77.5948 52.1615 75.8654C53.004 74.136 53.4065 72.2253 53.3333 70.3029C53.2725 67.9528 52.5129 65.674 51.1514 63.7575C56.8734 59.0722 63.6393 55.8335 70.8772 54.3154C78.1151 52.7972 85.6122 53.0442 92.7345 55.0354C99.8568 57.0266 106.395 60.7036 111.796 65.7553C117.197 70.807 121.303 77.085 123.765 84.0584C126.227 91.0318 126.974 98.4956 125.943 105.819C124.912 113.142 122.132 120.109 117.839 126.131C113.547 132.153 107.867 137.053 101.281 140.416C94.6945 143.78 87.3951 145.508 79.9999 145.454V145.454Z"
            fill="#0093A9"
            fill-opacity="0.4"
          />
          <path
            d="M89.6968 67.8787H70.3029C69.66 67.8787 69.0433 68.1341 68.5887 68.5887C68.1341 69.0433 67.8787 69.66 67.8787 70.3029C67.8787 70.9459 68.1341 71.5625 68.5887 72.0171C69.0433 72.4717 69.66 72.7271 70.3029 72.7271H89.6968C90.3398 72.7271 90.9564 72.4717 91.411 72.0171C91.8657 71.5625 92.1211 70.9459 92.1211 70.3029C92.1211 69.66 91.8657 69.0433 91.411 68.5887C90.9564 68.1341 90.3398 67.8787 89.6968 67.8787Z"
            fill="#0093A9"
            fill-opacity="0.4"
          />
          <path
            d="M89.6968 87.2727H70.3029C69.66 87.2727 69.0433 87.5281 68.5887 87.9827C68.1341 88.4374 67.8787 89.054 67.8787 89.6969C67.8787 90.3399 68.1341 90.9565 68.5887 91.4111C69.0433 91.8658 69.66 92.1212 70.3029 92.1212H89.6968C90.3398 92.1212 90.9564 91.8658 91.411 91.4111C91.8657 90.9565 92.1211 90.3399 92.1211 89.6969C92.1211 89.054 91.8657 88.4374 91.411 87.9827C90.9564 87.5281 90.3398 87.2727 89.6968 87.2727Z"
            fill="#0093A9"
            fill-opacity="0.4"
          />
          <path
            d="M89.6968 106.667H70.3029C69.66 106.667 69.0433 106.922 68.5887 107.377C68.1341 107.831 67.8787 108.448 67.8787 109.091C67.8787 109.734 68.1341 110.35 68.5887 110.805C69.0433 111.26 69.66 111.515 70.3029 111.515H89.6968C90.3398 111.515 90.9564 111.26 91.411 110.805C91.8657 110.35 92.1211 109.734 92.1211 109.091C92.1211 108.448 91.8657 107.831 91.411 107.377C90.9564 106.922 90.3398 106.667 89.6968 106.667Z"
            fill="#0093A9"
            fill-opacity="0.4"
          />
        </svg>
        <h4 class="c-skillset__skill-title">Content Strategy</h4>
        <p class="c-skillset__skill-subtext">
          The first step is always to understand what you’re trying to do and
          why you’re trying to do it. After that potentially energy zapping
          conversation, I will create a content map that highlights the best
          mediums, tone and strategy to meet your goal from the content and
          end-user stand point. It’s a lot of work, but my mum calls me
          “overzealous” so you’re in safe hands.
        </p>
      </div>
      <div class="c-skillset__skill">
        <svg
          width="200"
          height="194"
          viewBox="0 0 200 194"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
          class="c-skillset__skill-icon"
        >
          <path
            d="M161.729 67.6151C174.738 56.989 170.244 35.9751 153.988 31.62C149.741 30.4821 145.344 30.7187 141.313 32.2542L128.396 9.88238C123.14 0.778402 110.105 0.537147 104.508 9.41362C88.6213 34.6117 67.4566 56.0431 42.3293 72.3064C40.8984 73.2306 40.368 75.1407 41.2147 76.6953C41.3505 76.9441 62.7452 113.996 62.8869 114.242C63.8069 115.835 65.8445 116.383 67.4403 115.462C69.0345 114.541 69.5808 112.502 68.6604 110.908L48.5974 76.1574C72.5567 60.1403 93.7764 38.9352 110.148 12.9691C113.076 8.32442 119.882 8.46859 122.623 13.2158L168.872 93.3224C171.616 98.0758 168.326 104.036 162.848 104.249C132.115 105.447 102.026 113.307 74.5155 127.378C74.3984 127.437 43.2076 145.448 41.0597 146.688C35.4841 149.908 28.3298 147.99 25.1113 142.415L8.22717 113.17C5.00834 107.594 6.92547 100.44 12.5006 97.2212L32.8215 85.4888C34.4157 84.5684 34.962 82.5296 34.0416 80.9354C33.1211 79.3408 31.0819 78.7949 29.4881 79.7154L9.1672 91.4478C0.408644 96.5041 -2.6031 107.744 2.4537 116.503L19.3383 145.748C24.3955 154.507 35.6354 157.518 44.3939 152.461L45.1627 152.018L66.0086 188.124C69.0029 193.31 75.6239 195.087 80.8132 192.091L88.1246 187.87C93.3122 184.875 95.0864 178.253 92.0914 173.065L77.3172 147.476C76.3968 145.882 74.358 145.335 72.7638 146.256C71.1696 147.176 70.6233 149.215 71.5438 150.809L86.3179 176.399C87.4704 178.395 86.7879 180.943 84.7912 182.096L77.4798 186.317C75.4835 187.47 72.9351 186.787 71.7825 184.79L50.9366 148.684L77.6268 133.274C103.745 119.93 132.8 112.091 163.108 110.911C173.612 110.501 179.894 99.0775 174.646 89.9885L161.729 67.6151ZM160.776 44.592C164.067 50.2921 162.885 57.3657 158.33 61.7278L144.711 38.1385C150.681 36.3872 157.433 38.7998 160.776 44.592ZM193.38 29.772L184.755 34.7517C183.159 35.6726 181.122 35.1255 180.201 33.5317C179.281 31.9375 179.827 29.8987 181.422 28.9783L190.046 23.9986C191.642 23.0777 193.68 23.6248 194.6 25.2186C195.52 26.8128 194.974 28.8516 193.38 29.772ZM156.288 10.7732L158.391 2.92471C158.868 1.14633 160.695 0.0917193 162.474 0.567565C164.253 1.04424 165.308 2.87221 164.831 4.65017L162.728 12.4987C162.252 14.2725 160.429 15.3325 158.645 14.8558C156.867 14.3792 155.812 12.5516 156.288 10.7732ZM199.885 65.3659C199.486 66.8551 198.139 67.8372 196.667 67.8372C196.064 67.8372 196.486 67.9059 187.954 65.6196C186.175 65.1429 185.12 63.3154 185.597 61.537C186.073 59.7586 187.901 58.7044 189.679 59.1799L197.528 61.2828C199.306 61.7595 200.362 63.5875 199.885 65.3659Z"
            fill="#F594AB"
            fill-opacity="0.4"
          />
        </svg>
        <h4 class="c-skillset__skill-title">
          Product Marketing and Content Development
        </h4>
        <p class="c-skillset__skill-subtext">
          Finding the right customers for your product. I will work with your
          user research team and research similar products to determine who your
          ideal customers and build a marketing strategy that speaks directly to
          their needs in relation to your product. This will require visual
          communication written communication and content strategy to spark
          interest.
        </p>
      </div>
      <div class="c-skillset__skill">
        <svg
          width="150"
          height="165"
          viewBox="0 0 150 165"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
          class="c-skillset__skill-icon"
        >
          <path
            d="M34.035 119.78C35.4488 119.359 37.0922 118.705 38.9211 117.84C45.8658 114.31 51.898 108.965 57.7407 103.882C64.9609 97.6007 71.632 90.5412 77.8114 83.2445C86.8644 72.4831 95.2248 61.2357 102.592 49.2461C91.2838 62.089 80.0823 75.062 67.8861 87.0842C61.4101 93.4664 54.7332 99.6956 47.5513 105.282C43.8283 108.177 40.048 111 36.4417 114.042C34.9628 115.29 33.7155 116.464 32.6766 117.432C31.6455 118.412 30.8477 119.24 30.2948 119.791C29.7419 120.377 29.4473 120.688 29.4473 120.688C29.4473 120.688 29.8777 120.679 30.6812 120.57C31.4714 120.426 32.6403 120.235 34.035 119.78Z"
            fill="#ED484E"
            fill-opacity="0.4"
          />
          <path
            d="M95.3741 22.7109C91.829 34.2988 94.8882 41.3602 94.8882 41.3602C94.8882 41.3602 88.5901 38.8788 84.9532 32.4985C82.3456 35.4333 79.9236 38.5957 77.7273 42.0202C70.8936 57.333 75.0661 66.9867 75.0661 66.9867C75.0661 66.9867 71.3948 65.5403 67.9779 62.0297C61.9917 75.7909 56.6445 87.3425 52.6594 95.7182C61.7621 88.1135 70.8572 80.5164 78.9804 71.7925C87.5627 62.8639 96.0686 53.8185 104.22 44.4939C105.726 42.7969 107.01 41.2913 108.125 40.0879C110.32 37.6582 111.613 36.2884 111.613 36.2884C111.613 36.2884 110.792 37.9701 109.285 40.88C104.236 50.6293 98.4849 59.9023 92.3245 68.9802C83.306 82.2688 72.7015 94.9223 60.8362 105.896C72.5733 101.668 84.1229 95.8751 94.5074 88.8022C92.5312 88.521 90.5817 88.0331 88.6819 87.3291C88.0142 87.0134 87.4422 86.7456 86.9811 86.4988C86.0552 86.0282 85.5501 85.7412 85.5501 85.7412C85.5501 85.7412 86.1394 85.7584 87.1725 85.7909C92.0931 85.9401 96.9773 85.1711 101.609 83.6233C106.704 79.6364 111.414 75.3203 115.617 70.7192C111.077 70.7173 106.629 69.6211 102.652 67.354C103.067 67.5912 104.192 67.4152 104.676 67.4382C108.625 67.618 112.581 67.09 116.378 66.0129C117.913 65.5767 119.415 65.0448 120.892 64.4422C124.997 59.0892 128.404 53.413 130.914 47.4593C133.499 41.3353 135.852 35.7776 137.972 30.7901C133.558 31.5668 129.086 31.387 124.741 30.3347C124.741 30.3347 125.504 30.0306 126.841 29.5006C138.745 24.7752 144.97 13.744 149.183 2.3302C149.497 1.48077 149.763 0.704035 150 0C130.26 3.8588 110.8 10.5701 95.3741 22.7109Z"
            fill="#ED484E"
            fill-opacity="0.4"
          />
          <path
            d="M105.058 88.7219C103.474 88.7219 102.188 90.0056 102.188 91.5916V108.982C102.188 111.446 100.516 113.568 98.1211 114.144L65.8866 121.884C65.0716 122.079 64.3829 122.623 64.0022 123.369C63.6215 124.117 63.5851 124.991 63.9046 125.766L74.0557 150.424C74.6813 151.945 74.6086 153.566 73.9448 155.018L73.0992 156.353C71.9972 157.675 70.4342 158.456 68.6779 158.456H45.5136H5.73942V20.8743H89.3341C90.9181 20.8743 92.2038 19.5906 92.2038 18.0046C92.2038 16.4186 90.9181 15.1349 89.3341 15.1349H2.86971C1.28563 15.1349 0 16.4186 0 18.0046V161.324C0 162.91 1.28563 164.193 2.86971 164.193H45.5136H68.676C71.9551 164.193 75.0257 162.802 77.1971 160.424C77.2009 160.421 77.2028 160.417 77.2067 160.415C77.5912 159.994 77.9547 159.55 78.278 159.07C78.4215 158.856 78.5363 158.63 78.6626 158.41L106.216 114.892L106.175 114.903C107.274 113.178 107.926 111.153 107.926 108.984V91.5935C107.928 90.0056 106.642 88.7219 105.058 88.7219Z"
            fill="#ED484E"
            fill-opacity="0.4"
          />
          <path
            d="M67.465 42.399C67.465 40.813 66.1793 39.5293 64.5953 39.5293H24.4691C22.885 39.5293 21.5994 40.813 21.5994 42.399C21.5994 43.985 22.885 45.2687 24.4691 45.2687H64.5953C66.1793 45.2687 67.465 43.9831 67.465 42.399Z"
            fill="#ED484E"
            fill-opacity="0.4"
          />
          <path
            d="M54.182 63.6827C54.182 62.0967 52.8964 60.813 51.3123 60.813H24.4691C22.885 60.813 21.5994 62.0967 21.5994 63.6827C21.5994 65.2687 22.885 66.5524 24.4691 66.5524H51.3123C52.8964 66.5524 54.182 65.2668 54.182 63.6827Z"
            fill="#ED484E"
            fill-opacity="0.4"
          />
          <path
            d="M45.5136 84.9664C45.5136 83.3804 44.228 82.0967 42.6439 82.0967H24.4691C22.885 82.0967 21.5994 83.3804 21.5994 84.9664C21.5994 86.5524 22.885 87.8361 24.4691 87.8361H42.6439C44.228 87.8361 45.5136 86.5505 45.5136 84.9664Z"
            fill="#ED484E"
            fill-opacity="0.4"
          />
        </svg>
        <h4 class="c-skillset__skill-title">Copywriting</h4>
        <p class="c-skillset__skill-subtext">
          A multitalented royal, I will leverage my copywriting, storytelling,
          analytics, content strategy and delivery skills to grab the attention
          of the right audience and position your product as the market leader
          in your industry.
        </p>
      </div>
      <div class="c-skillset__skill">
        <svg
          width="200"
          height="200"
          viewBox="0 0 200 200"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
          class="c-skillset__skill-icon"
        >
          <g clip-path="url(#clip0)">
            <path
              d="M200 79.3189V79.3013C200 79.1345 199.991 78.9692 199.977 78.8048C199.973 78.7599 199.967 78.7153 199.962 78.6704C199.948 78.5415 199.93 78.4138 199.908 78.2872C199.9 78.2396 199.892 78.1919 199.882 78.1446C199.851 77.9903 199.816 77.8372 199.772 77.6868C199.768 77.672 199.764 77.6567 199.76 77.6419C199.714 77.488 199.661 77.3368 199.604 77.1876C199.582 77.1306 199.557 77.0747 199.534 77.0181C199.491 76.9173 199.445 76.8177 199.397 76.7196C199.369 76.6626 199.342 76.6052 199.312 76.5489C199.239 76.4118 199.161 76.2775 199.078 76.1462C199.046 76.0974 199.012 76.0505 198.979 76.0025C198.914 75.9068 198.846 75.813 198.776 75.7216C198.738 75.6728 198.7 75.6243 198.661 75.5763C198.558 75.4517 198.452 75.3298 198.338 75.2138C198.329 75.2048 198.321 75.1954 198.312 75.1864C198.191 75.0634 198.062 74.9474 197.929 74.8349C197.913 74.8208 197.899 74.8052 197.882 74.7915L187.891 66.5005V41.0204C187.891 33.4817 181.757 27.3485 174.219 27.3485H140.712L113.72 4.94815C105.77 -1.64873 94.2297 -1.64873 86.2797 4.94815L59.2875 27.3482H25.7812C18.2426 27.3482 12.1094 33.4814 12.1094 41.02V66.5001L2.11758 74.7923C2.10117 74.806 2.08672 74.8216 2.07031 74.8356C1.93789 74.9482 1.80898 75.0642 1.68789 75.1872C1.67891 75.1962 1.67031 75.2056 1.66133 75.2146C1.54844 75.3306 1.4418 75.4525 1.33906 75.5771C1.29961 75.6247 1.26172 75.6735 1.22383 75.7224C1.15312 75.8142 1.08555 75.9079 1.02031 76.0032C0.9875 76.0513 0.953125 76.0982 0.921875 76.147C0.838281 76.2778 0.760547 76.4122 0.6875 76.5497C0.657422 76.606 0.630469 76.6634 0.602734 76.7204C0.554297 76.8185 0.508984 76.9181 0.466016 77.0189C0.442187 77.0751 0.417969 77.1314 0.396094 77.1884C0.338281 77.3376 0.284766 77.4884 0.239453 77.6427C0.235156 77.6575 0.231641 77.6724 0.227344 77.6876C0.183984 77.838 0.148438 77.9911 0.117188 78.1454C0.107813 78.1931 0.0996094 78.2403 0.0914062 78.288C0.0691406 78.4146 0.0511719 78.5423 0.0371094 78.6712C0.0324219 78.7161 0.0265625 78.7607 0.0226562 78.8056C0.009375 78.9692 0 79.1345 0 79.3013V79.3189V79.322V178.512C0 184.652 2.59297 190.194 6.73672 194.113C6.8543 194.231 6.97227 194.347 7.09805 194.453C10.9094 197.896 15.9559 199.996 21.4844 199.996H178.516C184.045 199.996 189.091 197.896 192.903 194.452C193.028 194.347 193.145 194.231 193.262 194.115C197.406 190.195 200 184.652 200 178.512V79.322C200 79.3212 200 79.32 200 79.3189ZM25.7812 39.0669H174.219C175.296 39.0669 176.172 39.9431 176.172 41.02V86.5989L172.856 89.3505L106.237 144.637C102.623 147.636 97.377 147.635 93.7633 144.637L27.1437 89.3509L23.8281 86.5989V41.02C23.8281 39.9431 24.7043 39.0669 25.7812 39.0669ZM11.7188 178.512V91.7778L14.2391 93.8696C14.2406 93.8708 14.2422 93.8724 14.2438 93.8736L71.4582 141.354L12.3187 181.883C11.9309 180.832 11.7188 179.696 11.7188 178.512ZM80.8348 149.136L86.2797 153.654C94.2297 160.252 105.77 160.252 113.72 153.654L119.165 149.136L176.282 188.278H23.7172L80.8348 149.136ZM128.542 141.355L185.756 93.8736C185.757 93.8724 185.759 93.8708 185.761 93.8696L188.281 91.7778V178.512C188.281 179.696 188.069 180.832 187.681 181.883L128.542 141.355ZM93.7633 13.9665C97.377 10.9677 102.623 10.9677 106.237 13.9665L122.362 27.3485H77.6379L93.7633 13.9665Z"
              fill="#F3AB1D"
              fill-opacity="0.4"
            />
            <path
              d="M51.3672 64.4514C51.3672 67.6874 53.9906 70.3108 57.2266 70.3108H112.695C115.931 70.3108 118.555 67.6874 118.555 64.4514C118.555 61.2155 115.931 58.592 112.695 58.592H57.2266C53.9906 58.592 51.3672 61.2155 51.3672 64.4514Z"
              fill="#F3AB1D"
              fill-opacity="0.4"
            />
            <path
              d="M57.2266 93.7483H142.773C145.503 93.7483 147.79 91.8788 148.441 89.3522C148.562 88.8834 148.633 88.3952 148.633 87.8889C148.633 84.653 146.009 82.0295 142.773 82.0295H57.2266C53.9906 82.0295 51.3672 84.653 51.3672 87.8889C51.3672 88.3952 51.4383 88.8838 51.559 89.3522C52.2098 91.8792 54.4969 93.7483 57.2266 93.7483Z"
              fill="#F3AB1D"
              fill-opacity="0.4"
            />
          </g>
          <defs>
            <clipPath id="clip0">
              <rect width="200" height="200" fill="white" />
            </clipPath>
          </defs>
        </svg>
        <h4 class="c-skillset__skill-title">Content Manager</h4>
        <p class="c-skillset__skill-subtext">
          Need someone to execute or manage a specific part of your newsletters
          or subject-specific blog posts? Call me!
        </p>
      </div>
    </section>
    <p class="c-section-no">003</p>
    <section ref="contactSection" class="c-section c-contact">
      <h1 class="c-section__heading">Contact</h1>
      <p class="c-section__subtext">
        Now that you know a little about me, let’s talk about you
      </p>
      <div class="c-contact__links">
        <a href="" target="_blank">say hello</a>
        <a href="" target="_blank" class="c-link c-link--dashed">
          <svg
            width="115"
            height="47"
            viewBox="0 0 115 47"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M68.0592 7.6971C49.8087 7.6971 31.7253 6.91686 13.9861 11.7952C5.36498 14.166 1 24.6304 1 32.9773C1 35.8784 5.22391 36.7199 7.54625 37.3947C19.4675 40.859 32.1029 39.8221 44.3223 40.7743C54.7604 41.5876 64.8427 44.935 75.2441 45.9102C81.187 46.4673 88.1538 46.651 93.8982 44.7925C98.972 43.151 100.844 38.8197 103.957 34.7869C107.016 30.8238 110.862 26.6375 112.978 22.0669C113.996 19.8687 114.216 15.9464 112.393 14.1901C109.352 11.2617 105.207 10.2364 101.402 8.65508C94.7321 5.88299 87.8505 3.97176 80.7259 2.72088C70.429 0.913033 59.1128 0.812438 48.6865 1.73628C43.8617 2.1638 39.2228 3.34774 34.4764 4.2377C30.3032 5.02017 26.0992 5.38186 22.0225 6.63267C17.8115 7.92467 12.1422 11.4587 9.38239 14.8554C8.05659 16.4872 8.18491 17.6262 8.18491 19.6719"
              stroke="#F59494"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
          twitter
        </a>
        <a href="" target="_blank" class="c-link c-link--dashed">
          <svg
            width="159"
            height="50"
            viewBox="0 0 159 50"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M65.567 6.28683C50.8321 6.28683 34.6692 11.3701 20 13C13.2192 13.7534 10.9234 14.0406 5.62781 18.2772C-3.49253 25.5734 4.6798 33.6326 9.1135 42.5C12.4534 49.1798 16.7704 45.8616 23 48.5C27.9657 50.6031 35.6167 47.717 41 48.5C46.7619 49.3381 52.3297 49.3467 58 48.5C73.7919 46.1419 92.0899 46.909 108 48.5C115.365 49.2365 120.095 48.4486 127.5 48.5C132.062 48.5317 138.589 47.4983 143 46.126C147.957 44.584 151.283 46.9515 154.353 42.5C157.259 38.285 157.997 40.0391 158.271 35.0959C158.549 30.0973 158.177 27.7843 154.353 24.2471C150.158 20.3675 144.521 17.5933 138.714 17.3896C119.585 16.7184 100.683 11.8039 81.6043 10.532C70.065 9.7627 58.5993 10.8286 47.2075 8.20985C41.0512 6.7946 34.6407 3.88574 28.9933 1.06201"
              stroke="#AD94F5"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
          instagram
        </a>
        <a href="" target="_blank" class="c-link c-link--dashed">
          <svg
            width="107"
            height="17"
            viewBox="0 0 107 17"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M0.515381 6.21734C26.1344 6.21734 51.1998 1.38916 76.7316 1.38916C82.7093 1.38916 88.6871 1.38916 94.6648 1.38916C97.6887 1.38916 100.349 3.14911 103.287 3.45838C103.722 3.5042 105.627 3.99789 105.892 4.30139C107.912 6.60943 99.7821 4.84405 96.734 5.18273C92.2147 5.68488 87.6767 5.17495 83.1692 5.60423C78.5885 6.04049 73.9521 7.51574 69.4893 8.63142C59.9786 11.0091 49.7786 12.4691 40.0604 13.8045C31.7394 14.9478 23.7552 15.184 15.3831 15.184C12.9082 15.184 10.5592 15.8737 8.10252 15.8737C1.93823 15.8737 11.8185 15.8737 13.2372 15.8737C35.6034 15.8737 57.872 15.184 80.2186 15.184C88.3901 15.184 95.9573 11.7353 103.976 11.7353"
              stroke="#0B7F98"
              stroke-opacity="0.51"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
          linkedin
        </a>
      </div>
    </section>
    <section class="c-section c-footer">
      <div class="c-footer__column">
        <span>© 2020</span>
        <span class="c-footer__site-designer">
          Made in Lagos by
          <a
            href=""
            target="_blank"
            class="c-link c-link--green c-link--underline"
          >
            Kolapo</a
          >
          🤘🏾
        </span>
      </div>
      <div class="c-footer__column">Back to top</div>
      <div class="c-footer__column">Green mode</div>
    </section>
  </div>
</template>

<script>
import 'lazysizes'
import 'lazysizes/plugins/parent-fit/ls.parent-fit'

export default {
  mounted() {
    const observer = new IntersectionObserver(this.onElementObserved)

    const observableSections = [
      this.$refs.skillsetSection,
      this.$refs.contactSection,
    ]

    observableSections.forEach((section) => {
      observer.observe(section)
    })
  },
  methods: {
    onElementObserved(entries) {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          switch (entry.target) {
            case this.$refs.skillsetSection:
            case this.$refs.contactSection: {
              entry.target.style.setProperty('--h1-translate-value', '0px')
              entry.target.style.setProperty('--subtext-opacity', '1')
              entry.target.style.setProperty('--subtext-translate-value', '0px')
            }
          }
        }
      })
    },
  },
}
</script>

<style lang="scss" scoped>
.container {
  margin: 0 auto;
}

.c-section {
  width: 80%;
  margin: 0 auto;
  --h1-translate-value: 100%;
  --subtext-opacity: 0;
  --subtext-translate-value: 100%;

  &__heading {
    position: relative;
    font-size: 11.3rem;
    font-family: 'PlayfairDisplay';
    font-weight: normal;
    text-transform: uppercase;
    color: transparent;
    z-index: -1;

    &::after {
      position: absolute;
      content: '';
      width: 100%;
      height: 100%;
      left: 0;
      color: black;
      transform: translateY(var(--h1-translate-value));
      transition: transform 1.4s $easeOutExpo 0.2s;
    }

    &::before {
      position: absolute;
      content: '';
      width: 100%;
      height: 100%;
      background-color: $color-linen;
      transform: translateY(100%);
      z-index: 1;
    }
  }

  &__subtext {
    font-size: 3rem;
    line-height: 45px;
    margin-top: 60px;
    max-width: 750px;
    opacity: var(--subtext-opacity);
    transform: translateY(var(--subtext-translate-value));
    transition: transform 2s $easeOutExpo 0.4s, opacity 2s $easeOutExpo 0.5s;
  }
}

a,
.c-link {
  outline: none;
  text-decoration: none;

  &--green {
    --color: #{$color-green};
    color: var(--color);
  }

  &--red {
    --color: #{$color-red};
    color: var(--color);
  }

  &--underline {
    position: relative;

    &::after {
      content: '';
      position: absolute;
      width: 100%;
      height: 1.6px;
      color: inherit;
      background-color: var(--color);
      left: 0;
      bottom: 3px;
      transform: scaleX(0);
      transform-origin: left;
      transition: transform 0.8s $easeOutExpo;
    }

    &:hover {
      &::after {
        transform: scaleX(1);
      }
    }
  }
}

.c-section-no {
  font-family: 'Canela';
  font-size: 35rem;
  opacity: 0.1;
  text-align: right;
  transform: translateX(15px);
  margin: 200px 0px 60px;
}

.c-hero {
  display: flex;
  justify-content: space-between;
  margin-top: 148px;
  // $anim-duration: 1.4s;
  $anim-duration: 1.2s;
  $anim-delay: 0.3s;

  @keyframes slidein {
    to {
      transform: translateY(0%);
    }
  }

  @keyframes fadein {
    to {
      opacity: 1;
    }
  }

  @keyframes fadeout {
    to {
      opacity: 0;
    }
  }

  &__text {
    &-wrap {
      display: flex;
      flex-direction: column;
      padding-top: 70px;
      width: 50%;
      z-index: 1;
    }

    &-yogi {
      position: relative;
      color: $color-orange;

      &::after {
        content: '🧘🏽‍♀️';
        position: absolute;
        margin-left: 9px;
        opacity: 0;
        top: 0;
        transform: translateX(12%);
        transition: 1s $easeOutExpo;
        pointer-events: none;
      }

      &:hover {
        &::after {
          opacity: 1;
          transform: translateX(0%);
        }
      }
    }
  }

  .c-section__heading {
    text-transform: capitalize;
    white-space: nowrap;
    pointer-events: none;
    color: transparent;
    z-index: 0;
    // font-weight: 500;

    &::after {
      content: 'Adetomiwa Isiaka';
      width: 140%;
      animation: slidein $anim-duration $easeOutExpo $anim-delay forwards;
    }

    &::before {
      width: 140%;
      animation: fadeout 0s calc(#{$anim-delay} + 0.5s) forwards;
    }
  }

  .c-section__subtext {
    --subtext-translate-value: 15%;
    margin-top: 45px;
    max-width: 620px;
    width: 100%;
    animation: slidein calc(#{$anim-duration} + 0.5s) $easeOutExpo
        calc(#{$anim-delay} + 0.5s) forwards,
      fadein calc(#{$anim-duration} + 0.5s) $easeOutExpo
        calc(#{$anim-delay} + 0.6s) forwards;
  }

  &__image {
    position: relative;
    width: 525px;
    height: 80vh;
    max-height: 725px;
    overflow: hidden;
    z-index: 0;

    @keyframes scaleoverlay {
      to {
        transform: scaleY(0);
      }
    }

    @keyframes scaleimage {
      from {
        transform: scale(1.3);
      }
    }

    &-overlay {
      position: absolute;
      width: 100%;
      height: 100%;
      left: 0;
      z-index: 10;
      background-color: $color-linen;
      animation: scaleoverlay calc(#{$anim-duration} - 0.2s) $easeOutExpo
        calc(#{$anim-delay} + 0.6s) forwards;
      transform-origin: bottom;
    }

    img {
      transition: 1.2s $easeOutExpo;
      object-fit: cover;
      height: 100%;
      width: 100%;
      animation: scaleimage calc(#{$anim-duration} + 0.8s) $easeOutExpo
        calc(#{$anim-delay} + 0.6s);
      // filter: blur(25px);

      &:hover {
        transform: scale(1.05);
      }
    }
  }

  &__scroll {
    $size: 80px;
    position: relative;
    width: $size;
    height: $size;
    // background-color: $color-green;
    margin-top: auto;
    border-radius: 100px;
    // border: 0.5px solid rgb(134, 134, 134);
    display: flex;
    align-items: center;
    justify-content: center;
    transition: border 1s $easeOutExpo;
    opacity: 0;
    animation: fadein 0s linear 2s forwards;
    $anim-delay: 2s;
    $anim-duration: 0.42s;

    @keyframes drawcircle {
      to {
        stroke-dashoffset: 0;
      }
    }

    &::after {
      content: '';
      position: absolute;
      width: $size;
      height: $size;
      background-color: $color-green;
      transform: translate(45%, -30%) scale(0.8);
      border-radius: inherit;
      z-index: -1;
      pointer-events: none;
      opacity: 0;
      transition: transform 1s $easeOutExpo;
      animation: fadein calc(#{$anim-duration} + 0.6s) linear
        calc(#{$anim-delay} + 1s) forwards;
    }

    &-circle {
      position: absolute;
      width: 100%;
      height: 100%;
      --length: 375;
      stroke-dasharray: var(--length);
      stroke-dashoffset: var(--length);
      transform: rotate(-45deg);
      animation: drawcircle $anim-duration linear $anim-delay forwards;
    }

    &-arrow {
      $size: 25px;
      width: $size;
      height: $size;
      transform: translateY(-40%);
      opacity: 0;
      animation: slidein calc(#{$anim-duration} + 0.8s) $easeOutExpo
          calc(#{$anim-delay} + 0.3s) forwards,
        fadein calc(#{$anim-duration} + 0.4s) linear calc(#{$anim-delay} + 0.3s)
          forwards;

      path {
        transition: fill 1s $easeOutExpo;
      }
    }

    &:hover {
      border: 0.5px dashed transparent;

      .c-hero__scroll-circle {
        circle {
          stroke-width: 0;
        }
      }

      &::after {
        transform: translate(0%, 0%) scale(1);
      }

      svg path {
        fill: #f6eee3;
      }
    }
  }
}

.c-skillset {
  flex-direction: column;

  .c-section__heading {
    &::after {
      content: 'What I do';
    }
  }

  &__skill {
    display: flex;
    flex-direction: column;
    margin-top: 60px;

    &--first {
      margin-top: 85px;
    }

    &-icon {
      float: right;
      margin-left: auto;
      width: 250px;
      height: 250px;
    }

    &-title {
      font-size: 2.6rem;
      font-family: 'PlayfairDisplay';
      font-weight: 700;
      text-transform: uppercase;
    }

    &-subtext {
      max-width: 740px;
      // font-size: 2.5rem;
      // line-height: 40px;
      // margin-top: 20px;

      font-size: 3rem;
      line-height: 45px;
      margin-top: 30px;
    }
  }
}

.c-contact {
  flex-direction: column;

  .c-section__heading {
    &::after {
      content: 'Contact';
    }
  }

  &__links {
    display: flex;
    align-items: center;
    margin-top: 80px;
    font-weight: normal;
    text-transform: uppercase;

    a:first-child {
      $scale: 220px;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 100%;
      font-size: 2rem;
      width: $scale;
      height: $scale;
      color: $color-linen;
      background: $color-green;
      flex-shrink: 0;
      transition: 1.2s $easeOutExpo;

      &:hover {
        transform: scale(1.12);
      }
    }

    .c-link--dashed {
      position: relative;
      font-size: 2.4rem;
      margin-left: 68px;
      color: black;

      svg {
        position: absolute;
        stroke-width: 1.3px;
        transition: 0.4s linear;
      }

      &:nth-child(2) svg {
        --length: 330;
        left: -10px;
        top: -15px;
        stroke-dasharray: var(--length);
        stroke-dashoffset: var(--length);
      }

      &:nth-child(3) svg {
        --length: 390;
        top: -22px;
        left: -14px;
        stroke-dasharray: var(--length);
        stroke-dashoffset: var(--length);
      }

      &:last-child svg {
        --length: 307;
        stroke-dasharray: var(--length);
        stroke-dashoffset: var(--length);
        transform: translateY(100%);
      }

      &:hover svg {
        stroke-dashoffset: 0;
      }
    }
  }
}

.c-footer {
  margin-top: 165px;
  margin-bottom: 60px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 2rem;
  text-transform: uppercase;

  &__column {
    width: 33.33%;

    &:first-child {
      transform: translateY(-7%);
    }

    &:nth-child(2) {
      text-align: center;
    }

    &:last-child {
      text-align: right;
    }
  }

  &__site-designer {
    margin-left: 35px;
  }
}
</style>
