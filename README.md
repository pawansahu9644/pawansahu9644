- 👋 Hi, I’m @pawansahu9644
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
pawansahu9644/pawansahu9644 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
// Check for permission
if (ContextCompat.checkSelfPermission(this, Manifest.permission.CAMERA) != PackageManager.PERMISSION_GRANTED) {
    // Request the permission
    ActivityCompat.requestPermissions(this, new String[]{Manifest.permission.CAMERA}, CAMERA_PERMISSION_REQUEST_CODE);
} else {
    // Permission already granted, proceed with camera-related functionality
    openCamera();
}

// Handle the permission request result
@Override
public void onRequestPermissionsResult(int requestCode, @NonNull String[] permissions, @NonNull int[] grantResults) {
    super.onRequestPermissionsResult(requestCode, permissions, grantResults);
    if (requestCode == CAMERA_PERMISSION_REQUEST_CODE) {
        if (grantResults.length > 0 && grantResults[0] == PackageManager.PERMISSION_GRANTED) {
            // Permission granted, proceed with camera-related functionality
            openCamera();
        } else {
            // Permission denied, handle accordingly (e.g., show a message to the user)
            showPermissionDeniedMessage();
        }
    }
}

// Example function to open the camera (replace with your actual implementation)
private void openCamera() {
    // Code to open the camera
}

private void showPermissionDeniedMessage() {
    // Display a message to the user explaining why the permission is needed
}

// Define request codes
private static final int CAMERA_PERMISSION_REQUEST_CODE = 100;
