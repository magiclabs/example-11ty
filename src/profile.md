---
title: "Profile"
layout: "base.njk"
templateEngineOverride: njk,md
---

<!-- 0. HTML -->
<h3>Welcome ๐๐ผ</h3>
<h3 id="email"></h3>
<h3>Public Address ๐๐ผ</h3>
<h3 id="publicAddress"></h3>

<!-- 1. Ensure the userโs info is displayed -->
<script>
// Assumes a user is already logged in
const displayUserInfo = async () => {
  let emailElement = document.getElementById("email");
  let publicAddressElement = document.getElementById("publicAddress");
  try {
    const { email, publicAddress } = await magic.user.getMetadata();
    emailElement.innerHTML = email;
    publicAddressElement.innerHTML = publicAddress;
  } catch {
    // Handle errors if required!
    emailElement.innerHTML = "DNE";
    publicAddressElement.innerHTML = "DNE";
  }
};
displayUserInfo();
</script>
