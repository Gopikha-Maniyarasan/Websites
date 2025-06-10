<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Hospital Management</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet" />
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" />
  <style>
    body {
      background-color: #0cd4ef;
    }
    .navbar, footer {
      background-color: #111111;
    }
    .navbar-brand, .nav-link, footer {
      color: white !important;
    }
    .carousel-item img {
      height: 600px;
      object-fit: cover;
    }
    .carousel-caption {
      background-color: rgba(11, 1, 15, 0.6);
      border-radius: 10px;
      padding: 15px; /* Added padding for better appearance */
    }
    .carousel-caption h5.bold-title {
      font-size: 2rem;
      font-weight: bold;
      cursor: pointer;
    }

    /* Specific style for the "Hospital 24*7" title on the first carousel slide */
    .hospital-title-overlay {
        position: absolute;
        top: 20px; /* Adjust this value if needed to match the exact position in your screenshot */
        left: 50%;
        transform: translateX(-50%);
        text-align: center;
        /* To ensure the black background covers the text and has some padding */
        display: inline-block; /* Make it fit the content width */
        padding: 5px 15px;
        border-radius: 8px;
        z-index: 10;

        background-color: black; /* Solid black background for the container */
        color: #00BFFF; /* Default text color (DeepSkyBlue) for fallback */
        font-size: 2.5rem; /* Larger font size for prominence */
        font-weight: bold;
        text-shadow: 0 0 10px rgba(255, 255, 255, 0.7); /* Subtle glow effect */
    }

    /* The glitter effect for the text itself within the black background */
    .hospital-title-overlay span.glitter-text-inner {
        background-image: linear-gradient(45deg, #00BFFF, #ADD8E6, #00BFFF); /* Mass blue colors for glitter */
        background-size: 200% auto;
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        animation: shine 2s linear infinite;
        white-space: nowrap; /* Ensures the text stays on one line */
    }

    /* Original glitter-text for other sections - kept as per "no other changes" */
    .glitter-text {
      font-size: 2rem;
      font-weight: bold;
      background: linear-gradient(45deg, #ff00cc, #3333ff, #00ccff);
      background-size: 200% auto;
      color: #fff;
      background-clip: text;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      animation: shine 2s linear infinite;
      text-align: center;
    }
    @keyframes shine {
      to {
        background-position: 200% center;
      }
    }
    .surgery-img:hover, .dept-img:hover {
      transform: scale(1.05);
    }
    .social-icons a {
      color: rgb(7, 5, 5);
      margin: 0 10px;
      font-size: 20px;
    }
    .why-us {
      background-color: #b3e5fc;
      padding: 40px 20px;
      border-radius: 10px;
      margin-top: 60px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
    }
    .section-title {
      text-align: center;
      padding: 40px 0 20px;
    }
    /* Original .highlight class - kept as per "no other changes" */
    .highlight {
      background-color: black;
      color: #00BFFF; /* DeepSkyBlue – mass blue theme */
      font-weight: bold;
      padding: 4px 8px;
      border-radius: 6px;
    }
    .surgery-img, .dept-img {
      width: 100%;
      height: 250px;
      object-fit: cover;
      border-radius: 10px;
      transition: transform 0.3s;
      margin-bottom: 30px;
    }
    .why-us .features {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 30px;
    }
    .why-us .feature {
      background-color: white;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
      flex: 1 1 250px;
      max-width: 300px;
      text-align: center;
      cursor: pointer; /* Added cursor pointer to indicate clickability */
      transition: transform 0.2s ease-in-out;
    }
    .why-us .feature:hover {
      transform: translateY(-5px); /* Slight lift on hover */
    }
    .why-us .feature i {
      font-size: 40px;
      color: #0288d1;
      margin-bottom: 15px;
    }
    .why-us .feature h5 {
      font-weight: 600;
      margin-bottom: 10px;
      color: #01579b;
    }
    .why-us .feature p {
      font-size: 0.9rem;
      color: #444;
    }
    footer p {
      margin: 5px 0;
      color: #ccc;
    }
    .modal-img {
      max-width: 100%;
      height: 200px; /* Fixed height for modal images */
      object-fit: cover;
      border-radius: 8px;
      margin-bottom: 15px;
    }
  </style>
</head>
<body>
  <nav class="navbar navbar-expand-lg">
    <div class="container-fluid">
      <a class="navbar-brand d-flex align-items-center" href="#">
        <img src="Logoh.jpg" alt="Logo" width="40" height="40" class="me-2 rounded-circle" />
        <span>Hospital Management</span>
      </a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarContent">
        <img src="Logoh.jpg" alt="Toggle" width="30">
      </button>
      <div class="collapse navbar-collapse justify-content-end" id="navbarContent">
        <ul class="navbar-nav">
          <li class="nav-item"><a class="nav-link" href="#"><i class="fa fa-search"></i></a></li>
          <li class="nav-item"><a class="nav-link" href="https://wa.me/919876543210" target="_blank"><i class="fab fa-whatsapp"></i></a></li>
          <li class="nav-item"><a class="nav-link" href="https://instagram.com" target="_blank"><i class="fab fa-instagram"></i></a></li>
          <li class="nav-item"><a class="nav-link" href="https://facebook.com" target="_blank"><i class="fab fa-facebook-f"></i></a></li>
          <li class="nav-item"><a class="nav-link" href="https://twitter.com" target="_blank"><i class="fab fab-twitter"></i></a></li>
        </ul>
      </div>
    </div>
  </nav>

  <div id="hospitalCarousel" class="carousel slide" data-bs-ride="carousel">
    <div class="carousel-inner">
      <div class="carousel-item active">
        <img src="as1.jfif" class="d-block w-100" alt="Hospital" />
        <div class="hospital-title-overlay">
          <span class="glitter-text-inner">Hospital 24*7</span>
        </div>
        <div class="carousel-caption">
          <p style="color: white;">Best healthcare with modern facilities.</p>
        </div>
      </div>
      <div class="carousel-item">
        <img src="gslide2.jfif" class="d-block w-100" alt="About" />
        <div class="carousel-caption">
          <h5>About Our Hospital</h5>
          <p>Serving with excellence and dedication for over 20 years.</p>
        </div>
      </div>
      <div class="carousel-item">
        <img src="gs3.jfif" class="d-block w-100" alt="Care" />
        <div class="carousel-caption">
          <h5>Patient First</h5>
          <p>Compassionate care round the clock.</p>
        </div>
      </div>
      <div class="carousel-item">
        <img src="gs4.jfif" class="d-block w-100" alt="Emergency" />
        <div class="carousel-caption">
          <h5>24x7 Emergency Services</h5>
          <p>Immediate medical attention and ambulance services.</p>
        </div>
      </div>
      <div class="carousel-item">
        <img src="gs5.jfif" class="d-block w-100" alt="Advanced Operation Theatres" />
        <div class="carousel-caption">
          <h5>Advanced Operation Theatres</h5>
          <p>Equipped with modern technology for safe and successful surgeries.</p>
        </div>
      </div>
      <div class="carousel-item">
        <img src="gs6.jfif" class="d-block w-100" alt="Multi-Specialty Doctors" />
        <div class="carousel-caption">
          <h5>Multi-Specialty Doctors</h5>
          <p>Expert care from specialists in cardiology, neurology, pediatrics, and more.</p>
        </div>
      </div>
    </div>
    <button class="carousel-control-prev" type="button" data-bs-target="#hospitalCarousel" data-bs-slide="prev">
      <span class="carousel-control-prev-icon"></span>
    </button>
    <button class="carousel-control-next" type="button" data-bs-target="#hospitalCarousel" data-bs-slide="next">
      <span class="carousel-control-next-icon"></span>
    </button>
  </div>

  <section class="container">
    <h2 class="glitter-text"><u>About Us</u></h2>
    <p class="text-center">
      Our hospital delivers high-quality care using the latest technology, experienced professionals, and patient-centered services across various specialties.
    </p>
  </section>

  <section class="container mt-5">
    <h2 class="glitter-text">Types of Surgeries</h2>
    <ul>
      <li><strong>Cardiac Surgery</strong> – Heart bypass, valve repair</li>
      <li><strong>Orthopedic Surgery</strong> – Joint replacement, bone fractures</li>
      <li><strong>General Surgery</strong> – Appendix removal, hernia repair</li>
      <li><strong>Cancer Surgery</strong> – Cancer tissue removal</li>
      <li><strong>Cosmetic Surgery</strong> – Plastic, reconstructive procedures</li>
    </ul>
    <div class="row mt-4">
      <div class="col-md-4"><img src="Cardiologist Surgeon _ Fortis Healthcare.jfif" class="surgery-img" alt="Cardiac" /></div>
      <div class="col-md-4"><img src="Cervical cancer survival worse after common keyhole surgery, studies warn — The Independent.jfif" class="surgery-img" alt="Cardiac" /></div>
      <div class="col-md-4"><img src="Orthopedics Treatments in Bangalore.jfif" class="surgery-img" alt="Orthopedic" /></div>
      <div class="col-md-4 mt-4"><img src="General.jfif" class="surgery-img" alt="General" /></div>
      <div class="col-md-4 mt-4"><img src="Cos.jfif" class="surgery-img" alt="Cosmetic" /></div>
    </div>
  </section>

  <section class="container mt-5">
    <h2 class="glitter-text"><u>Advanced Surgeries</u></h2>
    <ul>
      <li><strong>Robotic Surgery</strong> – Minimally invasive with robotic assistance</li>
      <li><strong>Laser Surgery</strong> – Precise, reduced recovery time</li>
      <li><strong>Transplant Surgery</strong> – Organ transplants including kidney, liver</li>
      <li><strong>Endoscopic Surgery</strong> – Camera-guided instruments</li>
      <li><strong>Microsurgery</strong> – Tissue and nerve repair</li>
    </ul>
    <div class="row mt-4">
      <div class="col-md-4"><img src="Revolutionizing MedTech with Robot-Assisted Surgery.jfif" class="surgery-img" alt="Robotic" /></div>
      <div class="col-md-4"><img src="Shedding Light on Laser Eye Surgery_ Toledo Lasik.jfif" class="surgery-img" alt="Laser" /></div>
      <div class="col-md-4"><img src="Patient in Groundbreaking Heart Transplant Dies (Published 2022).jfif" class="surgery-img" alt="Transplant" /></div>
      <div class="col-md-4 mt-4"><img src="Endoscopy Equipment Market worth 34_82 Billion USD by 2022.jfif" class="surgery-img" alt="Endoscopic" /></div>
      <div class="col-md-4 mt-4"><img src="Microsurgery_ Vol 40, No 2.jfif" class="surgery-img" alt="Microsurgery" /></div>
    </div>
  </section>

  <section class="container mt-5">
    <h2 class="glitter-text">Our Mission</h2>
    <p class="text-center">
      We aim to deliver world-class medical care to every individual with compassion, safety, and the latest medical advancements. Your health is our responsibility.
    </p>
  </section>

  <section class="why-us container">
    <h2 class="glitter-text">Why Choose Us?</h2>
    <div class="features">
      <div class="feature" data-bs-toggle="modal" data-bs-target="#doctorsModal">
        <i class="fas fa-user-md"></i>
        <h5>Expert Doctors</h5>
        <p>Our experienced specialists provide the best diagnosis and treatment.</p>
      </div>
      <div class="feature" data-bs-toggle="modal" data-bs-target="#ambulanceModal">
        <i class="fas fa-ambulance"></i>
        <h5>24/7 Services</h5>
        <p>Round-the-clock emergency care and ambulance support.</p>
      </div>
      <div class="feature" data-bs-toggle="modal" data-bs-target="#facilitiesModal">
        <i class="fas fa-heartbeat"></i>
        <h5>Modern Facilities</h5>
        <p>Equipped with the latest machines for accurate diagnosis and treatment.</p>
      </div>
    </div>
  </section>

  <footer class="text-center p-4 mt-5">
    <p>© 2025 <strong>Hospital Management</strong>. Crafted By Gopikha❤️ in Chennai. All rights reserved.</p>
    <p>Call: 123456789 | Address: Hospital Street, Chennai.</p>
    <div class="social-icons">
      <a href="https://wa.me/919876543210" target="_blank"><i class="fab fa-whatsapp"></i></a>
      <a href="https://instagram.com" target="_blank"><i class="fab fa-instagram"></i></a>
      <a href="https://facebook.com" target="_blank"><i class="fab fa-facebook-f"></i></a>
      <a href="https://twitter.com" target="_blank"><i class="fab fa-twitter"></i></a>
    </div>
  </footer>

  <div class="modal fade" id="doctorsModal" tabindex="-1" aria-labelledby="doctorsModalLabel" aria-hidden="true">
    <div class="modal-dialog modal-dialog-centered modal-lg">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="doctorsModalLabel">Our Expert Doctors</h5>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body text-center">
          <p>We are proud to have a team of highly skilled and dedicated doctors who provide exceptional care across various specialties. Their expertise and commitment ensure the best possible outcomes for our patients.</p>
          <div class="row mt-3">
            <div class="col-md-4">
              <img src="Richard Zelman MD.jfif" class="modal-img" alt="Dr. Smith" />
              <p>Dr. Smith (Cardiologist)</p>
            </div>
            <div class="col-md-4">
              <img src="Future Prospects in the Neuromodulation Systems Market_ What to Expect (1).jfif" class="modal-img" alt="Dr. Johnson" />
              <p>Dr. Johnson (Neurologist)</p>
            </div>
            <div class="col-md-4">
              <img src="Orthopedics_ Specialized Care for the Musculoskeletal System.jfif" class="modal-img" alt="Dr. Brown" />
              <p>Dr. Brown (Orthopedic Surgeon)</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <div class="modal fade" id="ambulanceModal" tabindex="-1" aria-labelledby="ambulanceModalLabel" aria-hidden="true">
    <div class="modal-dialog modal-dialog-centered modal-lg">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="ambulanceModalLabel">24/7 Ambulance Services</h5>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body text-center">
          <p>Our ambulance services are available 24/7 to provide immediate and critical medical transport for various emergencies. We are equipped to handle:</p>
          <div class="row mt-3">
            <div class="col-md-4">
              <img src="Have you considered how doctors would establish your medical history in an emergency_ http___worldofexpats_com_why-accessing-your-medical-history-vital.jfif" class="modal-img" alt="Accident Emergency" />
              <p>Accident & Trauma Care</p>
            </div>
            <div class="col-md-4">
              <img src="47-4-pregnant-trauma.webp" class="modal-img" alt="Pregnancy Emergency" />
              <p>Maternity & Pediatric Transport</p>
            </div>
            <div class="col-md-4">
              <img src="1708268406651.jfif" class="modal-img" alt="Critical Care Transport" />
              <p>Critical Care Transport</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <div class="modal fade" id="facilitiesModal" tabindex="-1" aria-labelledby="facilitiesModalLabel" aria-hidden="true">
    <div class="modal-dialog modal-dialog-centered modal-lg">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="facilitiesModalLabel">Our Modern Facilities</h5>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body text-center">
          <p>We are equipped with state-of-the-art facilities and cutting-edge technology to provide comprehensive medical services and ensure patient comfort.</p>
          <div class="row mt-3">
            <div class="col-md-4">
              <img src="Intensive-Care-Unit-ICU-1.jpg" class="modal-img" alt="ICU" />
              <p>Intensive Care Unit (ICU)</p>
            </div>
            <div class="col-md-4">
              <img src="229A0223.jpg" class="modal-img" alt="Operation Theatre" />
              <p>Advanced Operation Theatres</p>
            </div>
            <div class="col-md-4">
              <img src="360_F_211045328_HnemU2NVFNwDWnQtDi5JHeHVhMV1jTOr.jpg" class="modal-img" alt="Lab" />
              <p>Diagnostic Labs</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html># Websites
Website Creation  with Full Stack 
