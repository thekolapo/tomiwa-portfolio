<template>
  <div id="#" class="container">
    <c-mouse ref="customCursor" />
    <c-image-loader v-if="heroImgIsLoading" ref="imgLoader" />
    <div v-else>
      <nav>
        <a class="c-link c-link--underline" href=".">Adetomiwa Isiaka</a>
        <a class="c-link c-link--underline" href="#contact">Get in touch</a>
      </nav>
      <section class="c-section c-hero">
        <div class="c-hero__text-wrap">
          <h1 class="c-section__heading">Adetomiwa Isiaka</h1>
          <p class="c-section__subtext">
            I’m a content developer currently working in Lagos, Nigeria.
            Presently, I work as a content strategist, copy writer, content
            writer and marketer at
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
              target="_blank"
              class="c-link c-link--green c-link--underline"
              >Global Voices</a
            >
            and a sometimes <span class="c-hero__text-yogi">yogi</span>.
          </p>
          <a v-if="showScrollIndicator" class="c-hero__scroll" href="#work">
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
          </a>
        </div>
        <div class="c-hero__image">
          <div class="c-hero__image-overlay" />
          <!-- <img
          id="js-hero-img"
          src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wCEAAEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAf/AABEIAA4ACgMBEQACEQEDEQH/xAGiAAABBQEBAQEBAQAAAAAAAAAAAQIDBAUGBwgJCgsQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+gEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoLEQACAQIEBAMEBwUEBAABAncAAQIDEQQFITEGEkFRB2FxEyIygQgUQpGhscEJIzNS8BVictEKFiQ04SXxFxgZGiYnKCkqNTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqCg4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2dri4+Tl5ufo6ery8/T19vf4+fr/2gAMAwEAAhEDEQA/APsT9tT9s39rjwD4z8Sa5+zfp2mj4IeBPgt8WPGHizxV4m8J6P4i0vWfiBJrPinTvCOiafbR3cmvSancI3htvD2mFdLttb+06vLHb64tjcLpv5vTw+BrQl7eDnTxGNwuHcnNwUIVMRTU5b2Sd5WlJ2Tj30f2NB1KkpV4YyVN4ahi6kMMqKm6840qkoXlJXUYRSbUbKyabu1f6i+Avxl8C+OPgZ8GPGvxE8QeA7H4geL/AIT/AA68UeOrL7LY6R9j8Y+IPCGj6t4ntf7KllMumfZ9bu76L+z5SZLLZ9mclojXh4qjQpYrE0qUU6VLEVqdN25r04VJRg+ZK0rxS1Wj3O2lOpOlTnPn5pU4Sl7sl70opvS2mrP5c/j3+3T4k0DxjceFP7b+IOh/D+9+G/hCG+8L+DrzSdKuvE9zYat4hBOr687G60vT7PU7Nrm2sLe31iO/aKGe5Nokz2EH2+XZb9YoLncZU415xqw5uRzScKluZ06is3y7RjJPmtJ6M8Gtj4YD2fJSVSu6SlCpVj7SnSupRXLR54RlLR3dRzjayVPdv7/8M/FP9oGfw34fmt/F2itbzaHpMsBurHRftJhksLd4jceV4M8rzyhUy+X+78zds+XFTKjkilJPJ4NqTTf1rEK7T1dk0tX2SXkc3tcweqzCaT1S+rUdPLc//9k="
          data-src="https://res.cloudinary.com/daitiebum/image/upload/v1604398570/tomiwa-website/tomiwa-min.jpg"
          class="lazyload"
          alt="tomiwa's picture"
        /> -->
          <img
            id="js-hero-img"
            src="https://res.cloudinary.com/daitiebum/image/upload/v1604398570/tomiwa-website/tomiwa-min.jpg"
            alt="tomiwa's picture"
          />
        </div>
      </section>
      <p class="c-section-no">002</p>
      <section id="work" ref="skillsetSection" class="c-section c-skillset">
        <h1 class="c-section__heading">What I do</h1>
        <p class="c-section__subtext">
          My goal is to help you craft the best formats and mediums to talk to
          your users with a productive mix of all my skillsets.
        </p>
        <div class="c-skillset__skill c-skillset__skill--content-strategy">
          <div class="c-skillset__skill-icon">
            <svg width="1400" height="158" viewBox="0 0 160 180" fill="none">
              <path
                d="M82.4242 19.5151V4.84848H89.6969C90.3399 4.84848 90.9565 4.59307 91.4111 4.13844C91.8658 3.6838 92.1212 3.06719 92.1212 2.42424C92.1212 1.78129 91.8658 1.16468 91.4111 0.710044C90.9565 0.255411 90.3399 0 89.6969 0H70.303C69.66 0 69.0434 0.255411 68.5888 0.710044C68.1342 1.16468 67.8788 1.78129 67.8788 2.42424C67.8788 3.06719 68.1342 3.6838 68.5888 4.13844C69.0434 4.59307 69.66 4.84848 70.303 4.84848H77.5757V19.5151C56.578 20.1517 36.6733 29.022 22.1603 44.2102C7.64736 59.3984 -0.309133 79.6857 0.00919679 100.691C0.327526 121.696 8.89514 141.732 23.8617 156.474C38.8282 171.215 58.9926 179.478 80 179.478C101.007 179.478 121.172 171.215 136.138 156.474C151.105 141.732 159.672 121.696 159.991 100.691C160.309 79.6857 152.353 59.3984 137.84 44.2102C123.327 29.022 103.422 20.1517 82.4242 19.5151V19.5151ZM80 174.545C65.1364 174.545 50.6066 170.138 38.248 161.88C25.8894 153.622 16.2571 141.885 10.5691 128.153C4.88102 114.421 3.39277 99.3105 6.29251 84.7326C9.19224 70.1546 16.3497 56.7639 26.8598 46.2538C37.37 35.7436 50.7607 28.5862 65.3386 25.6864C79.9166 22.7867 95.027 24.2749 108.759 29.963C122.491 35.651 134.228 45.2834 142.486 57.642C150.744 70.0006 155.151 84.5303 155.151 99.3939C155.151 119.325 147.234 138.44 133.14 152.534C119.046 166.628 99.9314 174.545 80 174.545V174.545Z"
                fill="#0093A9"
                fill-opacity="1"
              />
              <path
                d="M12.1212 33.9393C14.5185 33.9393 16.8621 33.2284 18.8554 31.8965C20.8487 30.5646 22.4023 28.6716 23.3197 26.4567C24.2372 24.2418 24.4772 21.8047 24.0095 19.4534C23.5418 17.1021 22.3874 14.9423 20.6922 13.2471C18.997 11.5519 16.8372 10.3975 14.4859 9.92981C12.1346 9.46211 9.69748 9.70215 7.48262 10.6196C5.26776 11.537 3.37469 13.0906 2.04279 15.0839C0.710897 17.0773 0 19.4208 0 21.8181C0 25.0329 1.27705 28.1159 3.55022 30.3891C5.82338 32.6623 8.90646 33.9393 12.1212 33.9393ZM12.1212 14.5454C13.5596 14.5454 14.9657 14.9719 16.1617 15.7711C17.3577 16.5702 18.2899 17.706 18.8403 19.035C19.3908 20.3639 19.5348 21.8262 19.2542 23.237C18.9736 24.6477 18.2809 25.9436 17.2638 26.9607C16.2467 27.9778 14.9508 28.6705 13.54 28.9511C12.1293 29.2317 10.667 29.0877 9.33805 28.5372C8.00914 27.9868 6.87329 27.0546 6.07415 25.8586C5.27502 24.6626 4.84848 23.2565 4.84848 21.8181C4.84848 19.8893 5.61471 18.0394 6.97861 16.6755C8.34251 15.3116 10.1924 14.5454 12.1212 14.5454Z"
                fill="#0093A9"
                fill-opacity="1"
              />
              <path
                d="M147.879 33.9393C150.276 33.9393 152.62 33.2284 154.613 31.8965C156.606 30.5646 158.16 28.6716 159.077 26.4567C159.995 24.2418 160.235 21.8047 159.767 19.4534C159.299 17.1021 158.145 14.9423 156.45 13.2471C154.755 11.5519 152.595 10.3975 150.244 9.92981C147.892 9.46211 145.455 9.70215 143.24 10.6196C141.025 11.537 139.132 13.0906 137.8 15.0839C136.468 17.0773 135.758 19.4208 135.758 21.8181C135.758 25.0329 137.035 28.1159 139.308 30.3891C141.581 32.6623 144.664 33.9393 147.879 33.9393ZM147.879 14.5454C149.317 14.5454 150.723 14.9719 151.919 15.7711C153.115 16.5702 154.047 17.706 154.598 19.035C155.148 20.3639 155.292 21.8262 155.012 23.237C154.731 24.6477 154.038 25.9436 153.021 26.9607C152.004 27.9778 150.708 28.6705 149.298 28.9511C147.887 29.2317 146.425 29.0877 145.096 28.5372C143.767 27.9868 142.631 27.0546 141.832 25.8586C141.033 24.6626 140.606 23.2565 140.606 21.8181C140.606 19.8893 141.372 18.0394 142.736 16.6755C144.1 15.3116 145.95 14.5454 147.879 14.5454V14.5454Z"
                fill="#0093A9"
                fill-opacity="1"
              />
              <path
                d="M79.9999 48.4847C68.1816 48.5576 56.7567 52.7402 47.6848 60.315C45.7825 58.9857 43.5319 58.2439 41.2121 58.1817C38.776 58.2208 36.4083 58.9931 34.4176 60.3978C32.427 61.8026 30.9059 63.7746 30.0527 66.0567C29.1996 68.3388 29.0539 70.8251 29.6348 73.1912C30.2156 75.5573 31.4961 77.6935 33.309 79.3211C30.5184 85.6446 29.0816 92.4819 29.0909 99.3938C29.0909 109.463 32.0766 119.305 37.6706 127.677C43.2645 136.049 51.2155 142.574 60.5179 146.428C69.8203 150.281 80.0564 151.289 89.9318 149.325C99.8072 147.36 108.878 142.512 115.998 135.392C123.118 128.272 127.966 119.201 129.931 109.326C131.895 99.4503 130.887 89.2142 127.034 79.9118C123.181 70.6093 116.655 62.6584 108.283 57.0645C99.9115 51.4705 90.0688 48.4847 79.9999 48.4847ZM41.2121 63.0302C42.6505 63.0302 44.0566 63.4567 45.2526 64.2559C46.4486 65.055 47.3807 66.1908 47.9312 67.5198C48.4816 68.8487 48.6257 70.311 48.345 71.7217C48.0644 73.1325 47.3718 74.4284 46.3547 75.4455C45.3375 76.4626 44.0417 77.1553 42.6309 77.4359C41.2201 77.7165 39.7578 77.5725 38.4289 77.022C37.1 76.4716 35.9642 75.5394 35.165 74.3434C34.3659 73.1474 33.9393 71.7413 33.9393 70.3029C33.9393 68.3741 34.7056 66.5242 36.0695 65.1603C37.4334 63.7964 39.2832 63.0302 41.2121 63.0302ZM79.9999 145.454C67.7839 145.454 56.0682 140.602 47.4302 131.964C38.7921 123.326 33.9393 111.61 33.9393 99.3938C33.922 93.3076 35.1599 87.2831 37.5757 81.6968C39.3783 82.3688 41.3189 82.5852 43.2252 82.327C45.1316 82.0688 46.9447 81.3439 48.5036 80.2167C50.0625 79.0895 51.319 77.5948 52.1615 75.8654C53.004 74.136 53.4065 72.2253 53.3333 70.3029C53.2725 67.9528 52.5129 65.674 51.1514 63.7575C56.8734 59.0722 63.6393 55.8335 70.8772 54.3154C78.1151 52.7972 85.6122 53.0442 92.7345 55.0354C99.8568 57.0266 106.395 60.7036 111.796 65.7553C117.197 70.807 121.303 77.085 123.765 84.0584C126.227 91.0318 126.974 98.4956 125.943 105.819C124.912 113.142 122.132 120.109 117.839 126.131C113.547 132.153 107.867 137.053 101.281 140.416C94.6945 143.78 87.3951 145.508 79.9999 145.454V145.454Z"
                fill="#0093A9"
                fill-opacity="1"
              />
              <path
                d="M89.6968 67.8787H70.3029C69.66 67.8787 69.0433 68.1341 68.5887 68.5887C68.1341 69.0433 67.8787 69.66 67.8787 70.3029C67.8787 70.9459 68.1341 71.5625 68.5887 72.0171C69.0433 72.4717 69.66 72.7271 70.3029 72.7271H89.6968C90.3398 72.7271 90.9564 72.4717 91.411 72.0171C91.8657 71.5625 92.1211 70.9459 92.1211 70.3029C92.1211 69.66 91.8657 69.0433 91.411 68.5887C90.9564 68.1341 90.3398 67.8787 89.6968 67.8787Z"
                fill="#0093A9"
                fill-opacity="1"
              />
              <path
                d="M89.6968 87.2727H70.3029C69.66 87.2727 69.0433 87.5281 68.5887 87.9827C68.1341 88.4374 67.8787 89.054 67.8787 89.6969C67.8787 90.3399 68.1341 90.9565 68.5887 91.4111C69.0433 91.8658 69.66 92.1212 70.3029 92.1212H89.6968C90.3398 92.1212 90.9564 91.8658 91.411 91.4111C91.8657 90.9565 92.1211 90.3399 92.1211 89.6969C92.1211 89.054 91.8657 88.4374 91.411 87.9827C90.9564 87.5281 90.3398 87.2727 89.6968 87.2727Z"
                fill="#0093A9"
                fill-opacity="1"
              />
              <path
                d="M89.6968 106.667H70.3029C69.66 106.667 69.0433 106.922 68.5887 107.377C68.1341 107.831 67.8787 108.448 67.8787 109.091C67.8787 109.734 68.1341 110.35 68.5887 110.805C69.0433 111.26 69.66 111.515 70.3029 111.515H89.6968C90.3398 111.515 90.9564 111.26 91.411 110.805C91.8657 110.35 92.1211 109.734 92.1211 109.091C92.1211 108.448 91.8657 107.831 91.411 107.377C90.9564 106.922 90.3398 106.667 89.6968 106.667Z"
                fill="#0093A9"
                fill-opacity="1"
              />
            </svg>
          </div>
          <h4 class="c-skillset__skill-title">Content Strategy</h4>
          <p class="c-section__subtext">
            The first step is always to understand what you’re trying to do and
            why you’re trying to do it. After that potentially energy zapping
            conversation, I will create a content map that highlights the best
            mediums, tone and strategy to meet your goal from the content and
            end-user stand point. It’s a lot of work, but my mum calls me
            “overzealous” so you’re in safe hands.
          </p>
        </div>
        <div class="c-skillset__skill c-skillset__skill--product-marketing">
          <div class="c-skillset__skill-icon">
            <svg
              width="291"
              height="291"
              viewBox="0 0 291 291"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M229.759 187.911C229.249 188.14 228.705 188.273 228.129 188.31L100.642 195.257C98.7498 195.362 96.9898 194.283 96.2133 192.552L73.7056 142.368C72.9291 140.637 73.2936 138.604 74.6303 137.261L164.605 46.6751C165.677 45.5918 167.189 45.1343 168.684 45.3983C170.17 45.6659 171.426 46.6501 172.045 48.0302L232.065 181.853C232.684 183.233 232.584 184.825 231.796 186.113C231.302 186.917 230.595 187.536 229.759 187.911V187.911ZM103.287 185.923L220.97 179.516L166.412 57.8704L83.36 141.494L103.287 185.923Z"
                fill="#F594AB"
                fill-opacity="1"
              />
              <path
                d="M102.271 194.858L72.9971 207.987C63.7717 212.125 52.9043 207.988 48.7667 198.762L37.5128 173.67C33.3752 164.445 37.5127 153.577 46.7382 149.44L76.012 136.31C78.3204 135.275 81.0342 136.308 82.0696 138.617L104.577 188.8C105.613 191.109 104.579 193.823 102.271 194.858ZM50.4894 157.804C45.8725 159.874 43.8061 165.302 45.8768 169.919L57.1306 195.011C59.2013 199.628 64.6289 201.694 69.2458 199.624L94.3377 188.37L75.5813 146.55L50.4894 157.804Z"
                fill="#F594AB"
                fill-opacity="1"
              />
              <path
                d="M145.258 245.903L120.166 257.157C118.083 258.091 115.632 257.352 114.413 255.417L79.7898 200.621C78.4395 198.484 79.0796 195.655 81.225 194.301C83.339 193.011 86.1909 193.591 87.5449 195.736L120.045 247.165L136.823 239.64L108.9 192.347C107.622 190.168 108.343 187.363 110.514 186.067C112.622 184.831 115.499 185.51 116.794 187.681L147.321 239.392C147.987 240.52 148.14 241.868 147.743 243.111C147.354 244.35 146.454 245.367 145.258 245.903V245.903Z"
                fill="#F594AB"
                fill-opacity="1"
              />
              <path
                d="M205.223 88.405C203.876 89.0089 202.262 88.9492 200.907 88.1003C198.768 86.7589 198.12 83.9252 199.47 81.7827L217.059 53.801C218.396 51.6743 221.222 51.0095 223.377 52.3639C225.515 53.7053 226.163 56.5391 224.814 58.6815L207.224 86.6633C206.727 87.4589 206.026 88.0448 205.223 88.405Z"
                fill="#F594AB"
                fill-opacity="1"
              />
              <path
                d="M264.076 152.427C263.273 152.787 262.369 152.921 261.444 152.763L228.85 147.289C226.36 146.869 224.667 144.504 225.087 142.014C225.513 139.513 227.893 137.832 230.362 138.252L262.957 143.726C265.446 144.147 267.14 146.512 266.719 149.001C266.452 150.578 265.423 151.823 264.076 152.427V152.427Z"
                fill="#F594AB"
                fill-opacity="1"
              />
              <path
                d="M243.444 106.425L218.352 117.679C216.044 118.714 213.33 117.681 212.295 115.373C211.259 113.064 212.292 110.35 214.601 109.315L239.693 98.0612C242.001 97.0258 244.715 98.0591 245.75 100.368C246.786 102.676 245.753 105.39 243.444 106.425Z"
                fill="#F594AB"
                fill-opacity="1"
              />
            </svg>
          </div>
          <h4 class="c-skillset__skill-title">
            Product Marketing and Content Development
          </h4>
          <p class="c-section__subtext">
            Finding the right customers for your product. I will work with your
            user research team and research similar products to determine who
            your ideal customers and build a marketing strategy that speaks
            directly to their needs in relation to your product. This will
            require visual communication written communication and content
            strategy to spark interest.
          </p>
        </div>
        <div
          ref="copywritingSection"
          class="c-skillset__skill c-skillset__skill--copywriting"
        >
          <div class="c-skillset__skill-icon">
            <svg width="108" height="150" viewBox="0 0 108 150" fill="none">
              <path
                d="M105.058 73.7218C103.474 73.7218 102.188 75.0055 102.188 76.5915V93.9819C102.188 96.4461 100.516 98.5677 98.1211 99.1436L65.8866 106.884C65.0716 107.079 64.3829 107.623 64.0022 108.369C63.6215 109.117 63.5851 109.991 63.9046 110.766L74.0557 135.424C74.6813 136.945 74.6086 138.566 73.9448 140.018L73.0992 141.353C71.9972 142.675 70.4342 143.456 68.6779 143.456H45.5136H5.73942V5.87418H89.3341C90.9181 5.87418 92.2038 4.59047 92.2038 3.00448C92.2038 1.41848 90.9181 0.134766 89.3341 0.134766H2.86971C1.28563 0.134766 0 1.41848 0 3.00448V146.324C0 147.91 1.28563 149.193 2.86971 149.193H45.5136H68.676C71.9551 149.193 75.0257 147.802 77.1971 145.424C77.2009 145.421 77.2028 145.417 77.2067 145.415C77.5912 144.994 77.9547 144.55 78.278 144.07C78.4215 143.856 78.5363 143.63 78.6626 143.41L106.216 99.8916L106.175 99.9031C107.274 98.1774 107.926 96.1533 107.926 93.9838V76.5934C107.928 75.0055 106.642 73.7218 105.058 73.7218Z"
                fill="#ED484E"
              />
              <path
                d="M83 35.4999C83 33.5655 81.2902 31.9999 79.1834 31.9999H25.8166C23.7099 31.9999 22 33.5655 22 35.4999C22 37.4342 23.7099 38.9999 25.8166 38.9999H79.1834C81.2902 38.9999 83 37.4319 83 35.4999Z"
                fill="#ED484E"
              />
              <path
                d="M70 56.4999C70 54.5655 68.106 52.9999 65.7724 52.9999H26.2276C23.894 52.9999 22 54.5655 22 56.4999C22 58.4342 23.894 59.9999 26.2276 59.9999H65.7724C68.106 59.9999 70 58.4319 70 56.4999Z"
                fill="#ED484E"
              />
              <path
                d="M56 77.4999C56 75.5655 54.1722 73.9999 51.92 73.9999H26.08C23.8278 73.9999 22 75.5655 22 77.4999C22 79.4342 23.8278 80.9999 26.08 80.9999H51.92C54.1722 80.9999 56 79.4319 56 77.4999Z"
                fill="#ED484E"
              />
              <rect
                x="102"
                y="32.9999"
                width="6"
                height="45"
                rx="3"
                fill="#ED484E"
              />
              <path
                d="M70.4048 109.974L95.0735 105.869L78.7839 133.536L70.4048 109.974Z"
                fill="var(--bg-color)"
              />
            </svg>
          </div>
          <h4 class="c-skillset__skill-title">Copywriting</h4>
          <p class="c-section__subtext">
            A multitalented royal, I will leverage my copywriting, storytelling,
            analytics, content strategy and delivery skills to grab the
            attention of the right audience and position your product as the
            market leader in your industry.
          </p>
        </div>
        <div
          ref="uxWritingSection"
          class="c-skillset__skill c-skillset__skill--ux-writing"
        >
          <div class="c-skillset__skill-icon">
            <svg
              height="512"
              viewBox="0 0 128 128"
              width="512"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="m112.654 4.75h-97.308a1.75 1.75 0 0 0 -1.746 1.75v115a1.75 1.75 0 0 0 1.75 1.75h97.308a1.749 1.749 0 0 0 1.75-1.75v-115a1.749 1.749 0 0 0 -1.754-1.75zm-1.75 115h-93.804v-111.5h93.8z"
              />
              <path
                d="m64 52.174h39.808a1.75 1.75 0 0 0 1.75-1.75v-26.232a1.751 1.751 0 0 0 -1.75-1.75h-39.808a1.751 1.751 0 0 0 -1.75 1.75v26.232a1.75 1.75 0 0 0 1.75 1.75zm1.75-26.232h36.308v22.732h-36.307z"
              />
              <path
                d="m24.193 25.942h30.141a1.75 1.75 0 0 0 0-3.5h-30.141a1.75 1.75 0 0 0 0 3.5z"
              />
              <path
                d="m24.191 39.21h30.14a1.75 1.75 0 0 0 0-3.5h-30.14a1.75 1.75 0 1 0 0 3.5z"
              />
              <path
                d="m24.191 52.48h30.14a1.75 1.75 0 0 0 0-3.5h-30.14a1.75 1.75 0 1 0 0 3.5z"
              />
              <path
                d="m103.809 62.25h-79.616a1.75 1.75 0 1 0 0 3.5h79.616a1.75 1.75 0 0 0 0-3.5z"
              />
              <path
                d="m103.809 75.52h-79.616a1.75 1.75 0 1 0 0 3.5h79.616a1.75 1.75 0 0 0 0-3.5z"
              />
              <path
                d="m103.809 88.788h-79.616a1.75 1.75 0 1 0 0 3.5h79.616a1.75 1.75 0 0 0 0-3.5z"
              />
              <path
                d="m103.809 102.058h-79.616a1.75 1.75 0 1 0 0 3.5h79.616a1.75 1.75 0 0 0 0-3.5z"
              />
            </svg>
          </div>
          <h4 class="c-skillset__skill-title">UX Writing</h4>
          <p class="c-section__subtext">
            As a UX writer my work involves leveraging my skills in creative
            writing, design and user research to create a clear, intuitive and
            comprehensive user experience; the highlight of my process is
            determining how a word used and placed a certain way might, at first
            glance, evoke an unmistakable feeling, compel a set of actions, and
            convince beyond doubt.
          </p>
        </div>
        <div
          ref="contentManagerSection"
          class="c-skillset__skill c-skillset__skill--content-manager"
        >
          <div class="c-skillset__skill-icon">
            <svg height="480pt" viewBox="0 0 480 480" width="480pt">
              <path
                d="m440 144h-8v-72c0-.175781-.089844-.320312-.097656-.496094-.046875-.71875-.191406-1.429687-.429688-2.113281-.089844-.253906-.152344-.503906-.265625-.75-.375-.84375-.898437-1.617187-1.542969-2.28125l-64-64c-.667968-.644531-1.445312-1.167969-2.296874-1.542969-.230469-.113281-.480469-.175781-.71875-.265625-.699219-.246093-1.429688-.390625-2.167969-.429687-.175781-.0312502-.3125-.121094-.480469-.121094h-280c-17.671875 0-32 14.328125-32 32v112h-8c-22.082031.027344-39.9726562 17.917969-40 40v256c.0273438 22.082031 17.917969 39.972656 40 40h400c22.082031-.027344 39.972656-17.917969 40-40v-256c-.027344-22.082031-17.917969-39.972656-40-40zm-244.558594 176h89.117188l136.800781 144h-362.71875zm244.558594-160c11.714844-.003906 21.71875 8.449219 23.671875 20l-31.671875 22.054688v-42.054688zm-35.3125-96h-28.6875c-4.417969 0-8-3.582031-8-8v-28.6875zm-340.6875-32c0-8.835938 7.164062-16 16-16h272v40c0 13.253906 10.746094 24 24 24h40v133.175781l-130.511719 90.824219h-90.976562l-130.511719-90.824219zm-24 128h8v42.054688l-31.671875-22.015626c1.933594-11.566406 11.945313-20.039062 23.671875-20.039062zm-24 280v-240.695312l163.785156 113.941406-142.984375 150.539062c-11.910156-1.601562-20.800781-11.769531-20.800781-23.785156zm427.199219 23.785156-142.984375-150.539062 163.785156-113.941406v240.695312c0 12.015625-8.890625 22.183594-20.800781 23.785156zm0 0"
              />
              <path
                d="m168 64h144c4.417969 0 8-3.582031 8-8s-3.582031-8-8-8h-144c-4.417969 0-8 3.582031-8 8s3.582031 8 8 8zm0 0"
              />
              <path
                d="m96 104c0 4.417969 3.582031 8 8 8h272c4.417969 0 8-3.582031 8-8s-3.582031-8-8-8h-272c-4.417969 0-8 3.582031-8 8zm0 0"
              />
              <path
                d="m376 144h-272c-4.417969 0-8 3.582031-8 8s3.582031 8 8 8h272c4.417969 0 8-3.582031 8-8s-3.582031-8-8-8zm0 0"
              />
              <path
                d="m376 192h-272c-4.417969 0-8 3.582031-8 8s3.582031 8 8 8h272c4.417969 0 8-3.582031 8-8s-3.582031-8-8-8zm0 0"
              />
              <path
                d="m328 240h-176c-4.417969 0-8 3.582031-8 8s3.582031 8 8 8h176c4.417969 0 8-3.582031 8-8s-3.582031-8-8-8zm0 0"
              />
              <path
                d="m88 80c4.417969 0 8-3.582031 8-8v-16c0-4.417969 3.582031-8 8-8h16c4.417969 0 8-3.582031 8-8s-3.582031-8-8-8h-16c-13.253906 0-24 10.746094-24 24v16c0 4.417969 3.582031 8 8 8zm0 0"
              />
            </svg>
          </div>
          <h4 class="c-skillset__skill-title">Content Manager</h4>
          <p class="c-section__subtext">
            Need someone to execute or manage a specific part of your
            newsletters or subject-specific blog posts? Call me!
          </p>
        </div>
      </section>
      <p class="c-section-no">003</p>
      <section id="contact" ref="contactSection" class="c-section c-contact">
        <h1 class="c-section__heading">Contact</h1>
        <p class="c-section__subtext">
          Now that you know a little about me, let’s talk about you
        </p>
        <div class="c-contact__links">
          <div>
            <a href="mailto:isiakatomiwa@gmail.com" target="_blank"
              >say hello</a
            >
          </div>
          <div>
            <a
              href="https://twitter.com/bellexsans"
              target="_blank"
              class="c-link c-link--dashed"
            >
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
            <a
              href="https://www.instagram.com/gurusista/"
              target="_blank"
              class="c-link c-link--dashed"
            >
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
            <a
              href="https://www.linkedin.com/in/adetomiwa-isiaka-11ba47107"
              target="_blank"
              class="c-link c-link--dashed"
            >
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
        </div>
      </section>
      <section ref="footer" class="c-section c-footer">
        <div class="c-footer__column">
          <span>© {{ new Date().getUTCFullYear() }}</span>
          <span class="c-footer__site-designer">
            <a
              href="https://twitter.com/kolapo_"
              target="_blank"
              class="c-link c-link--green c-link--underline"
            >
              Kolapo</a
            >
            🤘🏾
          </span>
        </div>
        <div class="c-footer__column"><a href="#">Back to top</a></div>
        <div class="c-footer__column">
          <button ref="footerButton" class="" @click="changeBGColor()">
            <span>{{ footerButtonText }}</span>
          </button>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      backgroundIsLightMode: true,
      defaultBackgroundColor: null,
      showScrollIndicator: true,
      footerButtonText: 'Green mode',
      heroImgIsLoading: true,
    }
  },
  mounted() {
    if (window.innerWidth <= 750) this.showScrollIndicator = false
    this.defaultBackgroundColor = window
      .getComputedStyle(document.body)
      .getPropertyValue('background-color')
  },
  methods: {
    init() {
      this.$refs.customCursor.init()
      const observer = new IntersectionObserver(this.onElementObserved)
      const observableSections = [
        this.$refs.skillsetSection,
        this.$refs.contactSection,
        this.$refs.copywritingSection,
        this.$refs.uxWritingSection,
        this.$refs.contentManagerSection,
      ]

      observableSections.forEach((section) => {
        observer.observe(section)
      })
    },
    hideImgLoader() {
      this.heroImgIsLoading = false
      setTimeout(() => {
        this.init()
      }, 10)
    },
    changeBGColor() {
      if (this.backgroundIsLightMode)
        document.body.style.setProperty('--bg-color', '#E3F6E8')
      else
        document.body.style.setProperty(
          '--bg-color',
          this.defaultBackgroundColor
        )

      const animateButton = () => {
        this.$refs.footerButton.style.setProperty('--translate-value', '-100%')
        // this.$refs.footerButton.style.pointerEvents = 'none'

        setTimeout(() => {
          this.$refs.footerButton.style.setProperty('--transition-time', '0s')
          this.$refs.footerButton.style.setProperty('--translate-value', '100%')

          setTimeout(() => {
            this.footerButtonText = this.backgroundIsLightMode
              ? 'Green mode'
              : 'Light mode'

            this.$refs.footerButton.style.setProperty(
              '--transition-time',
              '1.2s'
            )
            this.$refs.footerButton.style.setProperty('--translate-value', '0%')
            // this.$refs.footerButton.style.pointerEvents = 'auto'
          }, 50)
        }, 400)
      }

      animateButton()
      this.backgroundIsLightMode = !this.backgroundIsLightMode
    },
    onElementObserved(entries) {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          switch (entry.target) {
            case this.$refs.skillsetSection:
            case this.$refs.contactSection:
              entry.target.style.setProperty('--h1-translate-value', '0px')
              entry.target.style.setProperty('--subtext-opacity', '1')
              entry.target.style.setProperty('--subtext-translate-value', '0px')
              break

            case this.$refs.copywritingSection:
            case this.$refs.uxWritingSection:
            case this.$refs.contentManagerSection:
              entry.target.style.setProperty('--anim-play-state', 'running')
              break
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

@keyframes fadein {
  to {
    opacity: 1;
  }
}

nav,
.c-section {
  width: 80%;
  margin: 0 auto;

  @media screen and (max-width: 1440px) {
    width: 85%;
  }

  @media screen and (max-width: 1024px) {
    width: 90%;
  }

  @include screen('small') {
    width: 93%;
  }
}

nav {
  display: flex;
  justify-content: space-between;
  font-size: 1.8rem;
  font-weight: normal;
  text-transform: uppercase;
  margin-top: 30px;
  opacity: 0;
  animation: fadein 0.8s linear forwards;

  @media screen and (min-width: 1920px) {
    font-size: 1.07vw;
    margin-top: 1.79vw;
  }

  @include screen('small') {
    font-size: 1.6rem;
  }
}

.c-section {
  --h1-translate-value: 100%;
  --subtext-opacity: 0;
  --subtext-translate-value: 100%;

  @include screen('small') {
    --subtext-translate-value: 20%;
  }

  &__heading {
    position: relative;
    font-size: 11.3rem;
    font-family: 'PlayfairDisplay';
    font-weight: normal;
    text-transform: uppercase;
    color: transparent;
    z-index: -1;

    @media screen and (min-width: 1920px) {
      font-size: 6.73vw;
    }

    @media screen and (max-width: 1680px) {
      font-size: 6.73vw;
    }

    @media screen and (max-width: 1440px) {
      font-size: 6.6vw;
    }

    @media screen and (max-width: 1280px) {
      font-size: 6.4vw;
    }

    @media screen and (max-width: 1024px) {
      font-size: 6vw;
      font-weight: 500;
    }

    @include screen('med-small') {
      font-size: 10vw;
    }

    @include screen('small') {
      font-size: 3.4rem;
      font-weight: 600;
    }

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
      background-color: var(--bg-color);
      transition: var(--bg-color-transition);
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

    @media screen and (min-width: 1920px) {
      font-size: 1.786vw;
      line-height: 2.7vw;
      max-width: 44.64vw;
    }

    @media screen and (max-width: 1024px) {
      font-size: 2.8rem;
      line-height: 42px;
    }

    @include screen('med') {
      font-size: 2.6rem;
      line-height: 40px;
    }

    @include screen('small') {
      margin-top: 26px;
      font-size: 2.2rem;
      line-height: 32px;
    }
  }
}

a,
.c-link {
  outline: none;
  text-decoration: none;
  color: black;
  --color: black;

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

  @media screen and (min-width: 1920px) {
    font-size: 20vw;
    margin: 11.9vw 0px 3.57vw;
  }

  @media screen and (max-width: 1440px) {
    font-size: 33rem;
  }

  @media screen and (max-width: 1280px) {
    font-size: 31rem;
  }

  @media screen and (max-width: 1024px) {
    font-size: 28rem;
    margin-top: 140px;
  }

  @include screen('small') {
    font-size: 12rem;
    margin-top: 80px;
    transform: translateX(0px);
  }
}

.c-hero {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  margin-top: 110px;
  $anim-duration: 1.2s;
  $anim-delay: 0.3s;

  @keyframes slidein {
    to {
      transform: translateY(0%);
    }
  }

  @keyframes fadeout {
    to {
      opacity: 0;
    }
  }

  @media screen and (min-width: 1920px) {
    margin-top: 6.55vw;
  }

  @media screen and (max-width: 1440px) {
    margin-top: 90px;
  }

  @include screen('small') {
    margin-top: 50px;
  }

  &__text {
    &-wrap {
      display: flex;
      flex-direction: column;
      padding-top: 70px;
      width: 50%;
      z-index: 1;

      @include screen('med-small') {
        width: 100%;
      }

      @media screen and (max-width: 800px) {
        padding-top: 40px;
      }
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
      width: 100%;
      animation: slidein $anim-duration $easeOutExpo $anim-delay forwards;
    }

    &::before {
      width: 85vw;
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

    @media screen and (min-width: 1920px) {
      max-width: 36.9vw;
    }

    @include screen('med-small') {
      max-width: 100%;
    }

    @include screen('small') {
      margin-top: 26px;
    }
  }

  &__image {
    position: relative;
    width: 50%;
    height: 80vh;
    max-width: 525px;
    min-height: 640px;
    max-height: 725px;
    overflow: hidden;
    z-index: 0;

    @media screen and (min-width: 1920px) {
      max-width: 31.25vw;
      max-height: none;
      height: auto;
    }

    @include screen('med-small') {
      max-width: 100%;
      width: 100%;
      margin-top: 50px;
      min-height: auto;
      height: auto;
    }

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
      height: 101%;
      left: 0;
      z-index: 10;
      transform: scale(1.3);
      transform-origin: bottom;
      background-color: $color-linen;
      animation: scaleoverlay calc(#{$anim-duration} - 0.2s) $easeOutExpo
        calc(#{$anim-delay} + 0.6s) forwards;
    }

    img {
      transition: 1.2s $easeOutExpo;
      object-fit: cover;
      height: auto;
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
    margin-top: auto;
    border-radius: 100px;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: border 1s $easeOutExpo;
    opacity: 0;
    animation: fadein 0s linear 2s forwards;
    $anim-delay: 2s;
    $anim-duration: 0.42s;
    cursor: pointer;
    --arrow-size: 25px;

    @media screen and (min-width: 1920px) {
      $size: 4.76vw;
      margin-left: 0.5vw;

      &-arrow {
        --arrow-size: 1.49vw;
      }

      &-circle {
        width: $size;
        height: $size;
      }
    }

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
      border-radius: 100%;
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
      transform: rotate(-90deg);
      animation: drawcircle $anim-duration linear $anim-delay forwards;

      @media screen and (min-width: 1920px) {
        width: $size;
        height: $size;
      }
    }

    &-arrow {
      width: var(--arrow-size);
      height: var(--arrow-size);
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
    margin-top: 50px;

    @include screen('med') {
      margin-top: 100px;
    }

    @keyframes float {
      to {
        transform: translateY(-8%);
      }
    }

    &-icon {
      display: flex;
      --size: 250px;
      opacity: 0.4;
      float: right;
      margin-left: auto;
      width: var(--size);
      height: var(--size);
      animation: float 3s ease-in-out var(--icon-anim-delay) infinite alternate;

      @media screen and (min-width: 1920px) {
        --size: 14.9vw;
      }

      @media screen and (max-width: 1280px) {
        --size: 230px;
      }

      @include screen('med') {
        display: none;
      }

      svg {
        width: 100%;
        height: 100%;
        // margin-left: auto;
        margin: auto;

        path,
        rect {
          fill: black;
        }
      }
    }

    &-title {
      font-size: 2.6rem;
      font-family: 'PlayfairDisplay';
      font-weight: 700;
      text-transform: uppercase;

      @media screen and (min-width: 1920px) {
        font-size: 1.55vw;
      }

      @include screen('small') {
        font-size: 2.1rem;
      }
    }

    .c-section__subtext {
      max-width: 740px;
      margin-top: 30px;
      transition-property: none;

      @media screen and (min-width: 1920px) {
        max-width: 44vw;
      }

      @include screen('med') {
        max-width: 100%;
      }

      @include screen('small') {
        margin-top: 21px;
      }
    }

    &--content-strategy {
      --icon-anim-delay: 0s;
      margin-top: 85px;

      @keyframes rotatestopwatch {
        45% {
          transform: rotate(90deg);
        }

        100% {
          transform: rotate(90deg);
        }
      }

      svg {
        width: 77%;

        path {
          &:nth-child(4) {
            // display: none;
            transform-origin: 50% 55%;
            animation: rotatestopwatch 2.4s ease-in-out infinite 2.2s alternate;
          }
        }
      }
    }

    &--product-marketing {
      --icon-anim-delay: 2.7s;

      @keyframes speakerblare {
        28%,
        100% {
          opacity: 1;
        }
      }

      .c-skillset__skill-icon {
        // --size: 285px;

        path {
          // fill: #7ab1f2;
          &:nth-child(4),
          &:nth-child(5),
          &:nth-child(6) {
            opacity: 0;
            animation: speakerblare 2.4s ease-in-out infinite alternate;
          }
        }
      }
    }

    &--copywriting,
    &--ux-writing,
    &--content-manager {
      --anim-play-state: paused;

      @keyframes writenote {
        to {
          transform: scaleX(1);
        }
      }
    }

    &--copywriting {
      --icon-anim-delay: 1.9s;

      .c-skillset__skill-icon {
        svg {
          width: 55%;
          --delay-constant: 0.3s;

          path {
            &:nth-child(2),
            &:nth-child(3),
            &:nth-child(4) {
              --anim-delay: var(--delay-constant);
              --anim-duration: 0.6s;
              transform-origin: 20%;
              transform: scaleX(0);
              animation: writenote var(--anim-duration) ease-out
                var(--anim-delay) forwards var(--anim-play-state);
            }

            @for $i from 3 through 4 {
              &:nth-child(#{$i}) {
                --anim-delay: calc(
                  var(--delay-constant) +
                    (var(--anim-duration) - 0.1s) *
                    (#{$i} - 2)
                );
              }
            }

            &:last-of-type {
              fill: var(--bg-color);
            }
          }
        }
      }
    }

    &--ux-writing {
      --icon-anim-delay: 0.2s;

      .c-skillset__skill-icon {
        svg {
          width: 80%;
          --delay-constant: -0.6s;
          --anim-delay: var(--delay-constant);
          --anim-duration: 0.6s;

          path {
            @for $i from 3 through 9 {
              &:nth-child(#{$i}) {
                --anim-delay: calc(
                  var(--delay-constant) +
                    (var(--anim-duration) - 0.1s) *
                    (#{$i} - 2)
                );
                transform-origin: 18%;
                transform: scaleX(0);
                animation: writenote
                  var(--anim-duration)
                  ease-out
                  var(--anim-delay)
                  forwards
                  var(--anim-play-state);
              }
            }
          }
        }
      }
    }

    &--content-manager {
      --icon-anim-delay: 3.2s;

      .c-skillset__skill-icon {
        svg {
          width: 70%;
          --delay-constant: -0.4s;
          --anim-delay: var(--delay-constant);
          --anim-duration: 0.6s;

          path {
            @for $i from 2 through 6 {
              &:nth-child(#{$i}) {
                --anim-delay: calc(
                  var(--delay-constant) +
                    (var(--anim-duration) - 0.1s) *
                    (#{$i} - 1)
                );
                transform: scaleX(0);
                animation: writenote
                  var(--anim-duration)
                  ease-out
                  var(--anim-delay)
                  forwards
                  var(--anim-play-state);
              }
            }

            &:nth-child(2) {
              transform-origin: 34%;
            }

            &:nth-child(6) {
              transform-origin: 30%;
            }

            &:nth-child(3),
            &:nth-child(4),
            &:nth-child(5) {
              transform-origin: 20%;
            }
          }
        }
      }
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

    @media screen and (min-width: 1920px) {
      margin-top: 4.76vw;
    }

    @include screen('med-small') {
      & > :first-child {
        width: 35%;
      }

      & > :last-child {
        width: 20%;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        margin-left: 40px;

        @include screen('small') {
          margin-left: 30px;
        }

        a {
          &:first-child {
            margin-top: 0px;
          }
          margin-top: 30px;
        }
      }
    }

    @include screen('small') {
      margin-top: 60px;
    }

    & > :first-child a {
      --size: 220px;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 100%;
      font-size: 2rem;
      width: var(--size);
      height: var(--size);
      color: var(--bg-color);
      background: $color-green;
      flex-shrink: 0;
      transition: 1.2s $easeOutExpo;

      &:hover {
        transform: scale(1.12);
      }

      @media screen and (min-width: 1920px) {
        --size: 13.1vw;
        font-size: 1.19vw;
      }

      @include screen('small') {
        --size: 170px;
        font-size: 1.8rem;
      }
    }

    .c-link--dashed {
      position: relative;
      font-size: 2.4rem;
      margin-left: 68px;
      color: black;
      float: left;

      @media screen and (min-width: 1920px) {
        font-size: 1.43vw;
        margin-left: 4.05vw;
      }

      @include screen('med') {
        margin-left: 50px;
        font-size: 2.2rem;
      }

      @include screen('small') {
        font-size: 1.94rem;
      }

      svg {
        position: absolute;
        stroke-width: 1.3px;
        transition: 0.4s linear;
      }

      &:first-child svg {
        --length: 330;
        left: -10px;
        top: -15px;
        stroke-dasharray: var(--length);
        stroke-dashoffset: var(--length);
      }

      &:nth-child(2) svg {
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
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  font-size: 2rem;
  text-transform: uppercase;

  &__column {
    width: 33.33%;
    flex-shrink: 0;

    &:first-child {
      transform: translateY(-7%);
      z-index: 2;
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
    &::before {
      content: 'Made in Lagos by';
    }

    @include screen('small') {
      &::before {
        content: 'Made by';
      }
    }
  }

  @media screen and (min-width: 1920px) {
    font-size: 1.19vw;
    margin-top: 9.82vw;
    margin-bottom: 3.57vw;
  }

  @media screen and (max-width: 1270px) {
    &__column {
      width: 25%;

      &:first-child {
        width: 50%;
      }
    }

    &__site-designer {
      margin-left: 10px;
    }
  }

  @include screen('med-small') {
    &__column {
      width: 50%;

      &:first-child {
        width: 100%;
        display: flex;
        justify-content: space-between;
        margin-top: 25px;
        order: 3;
      }

      &:nth-child(2) {
        text-align: left;
      }
    }

    &__site-designer {
      transform: translateY(-20%);
    }
  }

  @include screen('small') {
    font-size: 1.7rem;
    margin-bottom: 40px;
    margin-top: 150px;
  }

  a,
  button {
    transition: color 0.3s linear;

    &:hover {
      color: $color-green;
    }
  }

  button {
    position: relative;
    background-color: transparent;
    border: none;
    text-transform: inherit;
    padding: 0;
    --translate-value: 0;
    --transition-time: 1s;

    span {
      display: inline-block;
      transform: translateY(var(--translate-value));
      transition: var(--transition-time) $easeOutExpo;
    }

    &::before,
    &::after {
      content: '';
      position: absolute;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      background-color: var(--bg-color);
      transition: var(--bg-color-transition);
      z-index: 1;
    }

    &::before {
      top: 100%;
    }

    &:after {
      bottom: 100%;
    }
  }
}
</style>
