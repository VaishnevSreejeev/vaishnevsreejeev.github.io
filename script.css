// script.js
document.addEventListener('DOMContentLoaded', () => {
    // --- CACHE DOM ELEMENTS ---
    const mobileMenuButton = document.getElementById('mobile-menu-button');
    const mobileMenu = document.getElementById('mobile-menu');
    const navLinks = document.querySelectorAll('.nav-link');
    const mobileNavLinks = document.querySelectorAll('.mobile-nav-link');
    const projectCards = document.querySelectorAll('.project-card');
    const modals = document.querySelectorAll('.modal');
    const modalOverlay = document.querySelector('.modal-overlay');

    // --- SMOOTH SCROLLING ---
    const smoothScrollTo = (selector) => {
        const element = document.querySelector(selector);
        if (element) {
            element.scrollIntoView({ behavior: 'smooth' });
        }
    };

    // --- MODAL LOGIC ---
    const openModal = (modalId) => {
        const modal = document.getElementById(modalId);
        if (modal) {
            modalOverlay.classList.add('active');
            modal.classList.add('active');
            document.body.style.overflow = 'hidden'; // Prevent background scrolling
        }
    };

    const closeModal = () => {
        modalOverlay.classList.remove('active');
        modals.forEach(modal => modal.classList.remove('active'));
        document.body.style.overflow = ''; // Restore scrolling
    };

    projectCards.forEach(card => {
        card.addEventListener('click', () => {
            const modalId = card.dataset.modalTarget;
            openModal(modalId);
        });
    });

    document.querySelectorAll('.modal-close-button').forEach(button => {
        button.addEventListener('click', closeModal);
    });
    modalOverlay.addEventListener('click', closeModal);

    // --- SCROLL REVEAL ANIMATION ---
    const revealOnScroll = () => {
        const revealElements = document.querySelectorAll('.reveal');
        const windowHeight = window.innerHeight;
        revealElements.forEach(el => {
            const elementTop = el.getBoundingClientRect().top;
            if (elementTop < windowHeight - 100) {
                el.classList.add('active');
            }
        });
    };
    window.addEventListener('scroll', revealOnScroll);
    setTimeout(revealOnScroll, 100); // Initial check

    // --- MOBILE MENU TOGGLE ---
    mobileMenuButton.addEventListener('click', () => {
        const isExpanded = mobileMenuButton.getAttribute('aria-expanded') === 'true';
        mobileMenuButton.setAttribute('aria-expanded', !isExpanded);
        mobileMenu.style.display = isExpanded ? 'none' : 'block';
        mobileMenuButton.innerHTML = isExpanded ? '☰' : '&times;';
    });

    // --- EVENT LISTENERS FOR NAVIGATION ---
    navLinks.forEach(link => {
        link.addEventListener('click', (e) => {
            e.preventDefault();
            smoothScrollTo(link.getAttribute('href'));
        });
    });

    mobileNavLinks.forEach(link => {
        link.addEventListener('click', (e) => {
            e.preventDefault();
            smoothScrollTo(link.getAttribute('href'));
            // Close mobile menu after clicking a link
            mobileMenu.style.display = 'none';
            mobileMenuButton.setAttribute('aria-expanded', 'false');
            mobileMenuButton.innerHTML = '☰';
        });
    });
});
