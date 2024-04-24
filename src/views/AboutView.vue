<template>
  <div class="about">
    <div class="content">
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas tempus
        interdum metus nec imperdiet. Integer non lectus est. Phasellus non
        dignissim purus, vel suscipit dolor. Sed vitae massa odio. Aliquam erat
        volutpat. Sed et eros felis. Aenean sed enim ligula. Nunc euismod,
        mauris in porttitor ullamcorper, mi quam elementum tortor, eget pulvinar
        urna ante porta libero. Quisque sed velit nec lorem vulputate volutpat
        eget pulvinar arcu. Sed id nulla mi.
      </p>
    </div>
  </div>
</template>

<style scoped>
.about {
  background-color: #4a9286; /* Green background */
  max-height: calc(
    100vh - 50px
  ); /* Subtract the navbar height from the viewport height */
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.content {
  background-color: #fff; /* White background for the text content */
  margin-bottom: 20px;
  padding: 20px;
  width: 80%; /* Content width less than the screen width */
  max-width: 600px; /* Maximum width for better readability */
  border-radius: 8px; /* Optional: adds rounded corners to the content box */
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); /* Optional: adds a subtle shadow for depth */
  height: 100%; /* Fills the available vertical space */
  overflow: auto; /* Adds scroll to content if it exceeds the container height */
}

.content p {
  color: #333; /* Dark grey text color for readability on white background */
}
</style>
