<script lang="ts">
  // You can add any script logic here for the contact page
</script>

<section class="py-16">
  <div class="container mx-auto px-6">
    <h1 class="text-5xl font-bold text-gray-800 mb-8 text-center">Contact Us</h1>
    <div class="max-w-2xl mx-auto bg-white p-8 rounded-lg shadow-lg">
      <p class="text-lg text-gray-700 mb-6 text-center">
        Have a question or want to start a project? Fill out the form below or reach out to us directly.
      </p>
      <form class="space-y-6">
        <div>
          <label for="name" class="block text-gray-700 text-sm font-bold mb-2">Name</label>
          <input
            type="text"
            id="name"
            name="name"
            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
            placeholder="Your Name"
          />
        </div>
        <div>
          <label for="email" class="block text-gray-700 text-sm font-bold mb-2">Email</label>
          <input
            type="email"
            id="email"
            name="email"
            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
            placeholder="your@example.com"
          />
        </div>
        <div>
          <label for="message" class="block text-gray-700 text-sm font-bold mb-2">Message</label>
          <textarea
            id="message"
            name="message"
            rows="6"
            class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
            placeholder="Your message here..."
          ></textarea>
        </div>
        <div class="text-center">
          <button
            type="submit"
            class="bg-blue-600 hover:bg-blue-700 text-white font-bold py-2 px-6 rounded-full focus:outline-none focus:shadow-outline transition-colors duration-300"
          >
            Send Message
          </button>
        </div>
      </form>
      <div class="mt-8 text-center text-gray-700">
        <p>Or contact us directly:</p>
        <p class="mt-2">Email: <a href="mailto:info@yourcompany.com" class="text-blue-600 hover:underline">info@yourcompany.com</a></p>
        <p>Phone: <a href="tel:+1234567890" class="text-blue-600 hover:underline">+1 (234) 567-890</a></p>
        <p>Address: 123 Business Rd, Suite 100, City, State, 12345</p>
      </div>
    </div>
  </div>
</section>
