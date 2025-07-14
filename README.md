<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cafe New Staff Onboarding Form</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f0f4f8; /* Light blue-grey background */
        }
        .form-container {
            max-width: 800px;
            margin: 2rem auto;
            padding: 2rem;
            background-color: #ffffff;
            border-radius: 12px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
        }
        .section-title {
            font-size: 1.5rem;
            font-weight: 600;
            color: #334155; /* Slate 700 */
            margin-bottom: 1.5rem;
            padding-bottom: 0.5rem;
            border-bottom: 1px solid #e2e8f0; /* Slate 200 */
        }
        .form-group label {
            display: block;
            font-weight: 500;
            color: #475569; /* Slate 600 */
            margin-bottom: 0.5rem;
        }
        .form-group input[type="text"],
        .form-group input[type="date"],
        .form-group select,
        .form-group textarea {
            width: 100%;
            padding: 0.75rem;
            border: 1px solid #cbd5e1; /* Slate 300 */
            border-radius: 8px;
            font-size: 1rem;
            color: #334155;
            transition: border-color 0.2s;
        }
        .form-group input[type="text"]:focus,
        .form-group input[type="date"]:focus,
        .form-group select:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #3b82f6; /* Blue 500 */
            box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.25);
        }
        .form-group textarea {
            min-height: 80px;
            resize: vertical;
        }
        .radio-group label,
        .checkbox-group label {
            display: flex;
            align-items: center;
            margin-bottom: 0.5rem;
            color: #475569;
        }
        .radio-group input[type="radio"],
        .checkbox-group input[type="checkbox"] {
            margin-right: 0.75rem;
            width: 1.25rem;
            height: 1.25rem;
            accent-color: #3b82f6;
        }
        .file-upload-label {
            display: inline-block;
            background-color: #3b82f6; /* Blue 500 */
            color: white;
            padding: 0.75rem 1.25rem;
            border-radius: 8px;
            cursor: pointer;
            transition: background-color 0.2s;
        }
        .file-upload-label:hover {
            background-color: #2563eb; /* Blue 600 */
        }
        .file-upload-input {
            display: none;
        }
        .file-name {
            margin-top: 0.5rem;
            font-size: 0.9rem;
            color: #64748b; /* Slate 500 */
        }
        .submit-button {
            background-color: #22c55e; /* Green 500 */
            color: white;
            padding: 1rem 2rem;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
            transition: background-color 0.2s;
            border: none;
            box-shadow: 0 4px 8px rgba(34, 197, 94, 0.2);
        }
        .submit-button:hover {
            background-color: #16a34a; /* Green 600 */
        }
        .message-box {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background-color: #4CAF50; /* Green */
            color: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            z-index: 1000;
            display: none; /* Hidden by default */
            text-align: center;
        }
        .message-box.error {
            background-color: #f44336; /* Red */
        }
        .message-box button {
            background-color: white;
            color: #4CAF50;
            border: none;
            padding: 8px 16px;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 10px;
        }
        .message-box.error button {
            color: #f44336;
        }
    </style>
</head>
<body>
    <div class="form-container">
        <h1 class="text-3xl font-bold text-center text-gray-800 mb-6">Cafe New Staff Onboarding Form</h1>
        <p class="text-center text-gray-600 mb-8">Welcome to the team! To help us get you set up, please complete this form with your details. All information will be kept confidential.</p>

        <!-- IMPORTANT: Replace "your_form_id" with your actual Formspree form ID -->
        <!-- You will need to set up a free account at formspree.io to get your ID -->
        <!-- Formspree will send the form data to the email address associated with your account -->
        <form id="onboardingForm" action="https://formspree.io/f/xovlakbo" method="POST" enctype="multipart/form-data">
            <!-- Section 1: Personal Details -->
            <div class="mb-8">
                <h2 class="section-title">Section 1: Personal Details</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mt-6">
                    <div class="form-group">
                        <label for="fullName">Full Name:</label>
                        <input type="text" id="fullName" name="Full Name" required class="rounded-lg">
                    </div>
                    <div class="form-group">
                        <label for="preferredName">Preferred Name:</label>
                        <input type="text" id="preferredName" name="Preferred Name" class="rounded-lg">
                    </div>
                    <div class="form-group">
                        <label for="dateOfBirth">Date of Birth:</label>
                        <input type="date" id="dateOfBirth" name="Date of Birth" required class="rounded-lg">
                    </div>
                    <div class="form-group">
                        <label for="gender">Gender:</label>
                        <select id="gender" name="Gender" class="rounded-lg">
                            <option value="">Select...</option>
                            <option value="Male">Male</option>
                            <option value="Female">Female</option>
                            <option value="Non-binary">Non-binary</option>
                            <option value="Prefer not to say">Prefer not to say</option>
                        </select>
                    </div>
                </div>
                <div class="form-group mt-6">
                    <label for="residentialAddress">Residential Address:</label>
                    <textarea id="residentialAddress" name="Residential Address" rows="3" placeholder="Street, Suburb, State, Postcode" required class="rounded-lg"></textarea>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mt-6">
                    <div class="form-group">
                        <label for="mobileNumber">Mobile Number:</label>
                        <input type="text" id="mobileNumber" name="Mobile Number" required class="rounded-lg">
                    </div>
                    <div class="form-group">
                        <label for="emailAddress">Email Address:</label>
                        <input type="text" id="emailAddress" name="Email Address" required class="rounded-lg">
                    </div>
                </div>

                <div class="form-group mt-6">
                    <label>Are you an Australian Citizen or Permanent Resident?</label>
                    <div class="radio-group flex space-x-4 mt-2">
                        <label>
                            <input type="radio" name="Citizenship" value="Yes" onchange="toggleVisaFields(false)"> Yes
                        </label>
                        <label>
                            <input type="radio" name="Citizenship" value="No" onchange="toggleVisaFields(true)"> No
                        </label>
                    </div>
                </div>

                <div id="visaFields" class="hidden mt-4 bg-blue-50 p-4 rounded-lg border border-blue-200">
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div class="form-group">
                            <label for="visaType">Visa Type:</label>
                            <input type="text" id="visaType" name="Visa Type" class="rounded-lg">
                        </div>
                        <div class="form-group">
                            <label for="visaExpiryDate">Visa Expiry Date:</label>
                            <input type="date" id="visaExpiryDate" name="Visa Expiry Date" class="rounded-lg">
                        </div>
                    </div>
                    <div class="form-group mt-4">
                        <label for="visaUpload">Please upload a copy of your Visa (if applicable):</label>
                        <label class="file-upload-label">
                            Upload Visa
                            <input type="file" id="visaUpload" name="Visa Upload" accept=".pdf,.jpg,.png" class="file-upload-input" onchange="displayFileName('visaUpload', 'visaFileName')">
                        </label>
                        <span id="visaFileName" class="file-name">No file chosen</span>
                    </div>
                </div>

                <div class="form-group mt-6">
                    <label for="tfn">Tax File Number (TFN):</label>
                    <input type="text" id="tfn" name="Tax File Number (TFN)" required class="rounded-lg">
                </div>

                <div class="form-group mt-6">
                    <label>Do you have a current NSW Responsible Service of Alcohol (RSA) certificate?</label>
                    <div class="radio-group flex space-x-4 mt-2">
                        <label>
                            <input type="radio" name="Has RSA" value="Yes" onchange="toggleCertificateUpload('rsaUploadGroup', true)"> Yes
                        </label>
                        <label>
                            <input type="radio" name="Has RSA" value="No" onchange="toggleCertificateUpload('rsaUploadGroup', false)"> No
                        </label>
                    </div>
                    <div id="rsaUploadGroup" class="hidden mt-4 bg-green-50 p-4 rounded-lg border border-green-200">
                        <label for="rsaUpload">Please upload a copy of your RSA certificate:</label>
                        <label class="file-upload-label">
                            Upload RSA
                            <input type="file" id="rsaUpload" name="RSA Upload" accept=".pdf,.jpg,.png" class="file-upload-input" onchange="displayFileName('rsaUpload', 'rsaFileName')">
                        </label>
                        <span id="rsaFileName" class="file-name">No file chosen</span>
                    </div>
                </div>

                <div class="form-group mt-6">
                    <label>Do you have a current NSW Responsible Conduct of Gambling (RCG) certificate?</label>
                    <div class="radio-group flex space-x-4 mt-2">
                        <label>
                            <input type="radio" name="Has RCG" value="Yes" onchange="toggleCertificateUpload('rcgUploadGroup', true)"> Yes
                        </label>
                        <label>
                            <input type="radio" name="Has RCG" value="No" onchange="toggleCertificateUpload('rcgUploadGroup', false)"> No
                        </label>
                    </div>
                    <div id="rcgUploadGroup" class="hidden mt-4 bg-green-50 p-4 rounded-lg border border-green-200">
                        <label for="rcgUpload">Please upload a copy of your RCG certificate:</label>
                        <label class="file-upload-label">
                            Upload RCG
                            <input type="file" id="rcgUpload" name="RCG Upload" accept=".pdf,.jpg,.png" class="file-upload-input" onchange="displayFileName('rcgUpload', 'rcgFileName')">
                        </label>
                        <span id="rcgFileName" class="file-name">No file chosen</span>
                    </div>
                </div>
            </div>

            <!-- Section 2: Employment Details -->
            <div class="mb-8">
                <h2 class="section-title">Section 2: Employment Details</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mt-6">
                    <div class="form-group">
                        <label for="startDate">Start Date:</label>
                        <input type="date" id="startDate" name="Start Date" required class="rounded-lg">
                    </div>
                    <div class="form-group">
                        <label for="position">Position:</label>
                        <input type="text" id="position" name="Position" placeholder="e.g., Barista, Waitstaff, Chef" required class="rounded-lg">
                    </div>
                    <div class="form-group">
                        <label for="desiredHours">Desired Hours (per week, approximate):</label>
                        <input type="text" id="desiredHours" name="Desired Hours" placeholder="e.g., 20-25 hours" class="rounded-lg">
                    </div>
                </div>

                <div class="form-group mt-6">
                    <label>Availability:</label>
                    <div class="bg-gray-50 p-4 rounded-lg border border-gray-200">
                        <div class="grid grid-cols-4 gap-2 text-sm font-medium text-gray-700 mb-2">
                            <div>Day</div>
                            <div>Morning</div>
                            <div>Afternoon</div>
                            <div>Evening</div>
                        </div>
                        <!-- Availability Grid -->
                        <div class="grid grid-cols-4 gap-2 availability-row">
                            <div>Monday</div>
                            <label><input type="checkbox" name="Availability_Monday_Morning" class="rounded"> </label>
                            <label><input type="checkbox" name="Availability_Monday_Afternoon" class="rounded"> </label>
                            <label><input type="checkbox" name="Availability_Monday_Evening" class="rounded"> </label>
                        </div>
                        <div class="grid grid-cols-4 gap-2 availability-row">
                            <div>Tuesday</div>
                            <label><input type="checkbox" name="Availability_Tuesday_Morning" class="rounded"> </label>
                            <label><input type="checkbox" name="Availability_Tuesday_Afternoon" class="rounded"> </label>
                            <label><input type="checkbox" name="Availability_Tuesday_Evening" class="rounded"> </label>
                        </div>
                        <div class="grid grid-cols-4 gap-2 availability-row">
                            <div>Wednesday</div>
                            <label><input type="checkbox" name="Availability_Wednesday_Morning" class="rounded"> </label>
                            <label><input type="checkbox" name="Availability_Wednesday_Afternoon" class="rounded"> </label>
                            <label><input type="checkbox" name="Availability_Wednesday_Evening" class="rounded"> </label>
                        </div>
                        <div class="grid grid-cols-4 gap-2 availability-row">
                            <div>Thursday</div>
                            <label><input type="checkbox" name="Availability_Thursday_Morning" class="rounded"> </label>
                            <label><input type="checkbox" name="Availability_Thursday_Afternoon" class="rounded"> </label>
                            <label><input type="checkbox" name="Availability_Thursday_Evening" class="rounded"> </label>
                        </div>
                        <div class="grid grid-cols-4 gap-2 availability-row">
                            <div>Friday</div>
                            <label><input type="checkbox" name="Availability_Friday_Morning" class="rounded"> </label>
                            <label><input type="checkbox" name="Availability_Friday_Afternoon" class="rounded"> </label>
                            <label><input type="checkbox" name="Availability_Friday_Evening" class="rounded"> </label>
                        </div>
                        <div class="grid grid-cols-4 gap-2 availability-row">
                            <div>Saturday</div>
                            <label><input type="checkbox" name="Availability_Saturday_Morning" class="rounded"> </label>
                            <label><input type="checkbox" name="Availability_Saturday_Afternoon" class="rounded"> </label>
                            <label><input type="checkbox" name="Availability_Saturday_Evening" class="rounded"> </label>
                        </div>
                        <div class="grid grid-cols-4 gap-2 availability-row">
                            <div>Sunday</div>
                            <label><input type="checkbox" name="Availability_Sunday_Morning" class="rounded"> </label>
                            <label><input type="checkbox" name="Availability_Sunday_Afternoon" class="rounded"> </label>
                            <label><input type="checkbox" name="Availability_Sunday_Evening" class="rounded"> </label>
                        </div>
                    </div>
                </div>

                <div class="form-group mt-6">
                    <label for="unavailableTimes">Are there any days/times you are NOT available to work?</label>
                    <textarea id="unavailableTimes" name="Unavailable Times" rows="3" class="rounded-lg"></textarea>
                </div>
            </div>

            <!-- Section 3: Bank Details for Payroll -->
            <div class="mb-8">
                <h2 class="section-title">Section 3: Bank Details for Payroll</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mt-6">
                    <div class="form-group">
                        <label for="bankName">Bank Name:</label>
                        <input type="text" id="bankName" name="Bank Name" required class="rounded-lg">
                    </div>
                    <div class="form-group">
                        <label for="accountName">Account Name:</label>
                        <input type="text" id="accountName" name="Account Name" required class="rounded-lg">
                    </div>
                    <div class="form-group">
                        <label for="bsb">BSB:</label>
                        <input type="text" id="bsb" name="BSB" pattern="[0-9]{6}" title="BSB must be 6 digits" required class="rounded-lg">
                    </div>
                    <div class="form-group">
                        <label for="accountNumber">Account Number:</label>
                        <input type="text" id="accountNumber" name="Account Number" required class="rounded-lg">
                    </div>
                </div>
            </div>

            <!-- Section 4: Superannuation Details -->
            <div class="mb-8">
                <h2 class="section-title">Section 4: Superannuation Details</h2>
                <div class="form-group mt-6">
                    <label>Do you have an existing Superannuation Fund?</label>
                    <div class="radio-group flex space-x-4 mt-2">
                        <label>
                            <input type="radio" name="Has Existing Super Fund" value="Yes" onchange="toggleSuperFundFields(true)"> Yes
                        </label>
                        <label>
                            <input type="radio" name="Has Existing Super Fund" value="No" onchange="toggleSuperFundFields(false)"> No
                        </label>
                    </div>
                </div>

                <div id="superFundFields" class="hidden mt-4 bg-yellow-50 p-4 rounded-lg border border-yellow-200">
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div class="form-group">
                            <label for="superFundName">Super Fund Name:</label>
                            <input type="text" id="superFundName" name="Super Fund Name" class="rounded-lg">
                        </div>
                        <div class="form-group">
                            <label for="superFundABN">Super Fund ABN:</label>
                            <input type="text" id="superFundABN" name="Super Fund ABN" class="rounded-lg">
                        </div>
                        <div class="form-group">
                            <label for="superFundUSI">Super Fund USI (Unique Superannuation Identifier):</label>
                            <input type="text" id="superFundUSI" name="Super Fund USI" class="rounded-lg">
                        </div>
                        <div class="form-group">
                            <label for="memberNumber">Your Member Number:</label>
                            <input type="text" id="memberNumber" name="Super Member Number" class="rounded-lg">
                        </div>
                    </div>
                </div>

                <div id="defaultSuperInfo" class="hidden mt-4 bg-blue-50 p-4 rounded-lg border border-blue-200">
                    <p class="text-gray-700">If you do not have an existing superannuation fund, we will set you up with our default fund, **[Your Cafe's Default Super Fund Name]**. You will receive details directly from them.</p>
                </div>
            </div>

            <!-- Section 5: Emergency Contact Details -->
            <div class="mb-8">
                <h2 class="section-title">Section 5: Emergency Contact Details</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mt-6">
                    <div class="form-group">
                        <label for="emergencyContactName">Full Name of Emergency Contact:</label>
                        <input type="text" id="emergencyContactName" name="Emergency Contact Name" required class="rounded-lg">
                    </div>
                    <div class="form-group">
                        <label for="emergencyContactRelationship">Relationship to you:</label>
                        <input type="text" id="emergencyContactRelationship" name="Emergency Contact Relationship" required class="rounded-lg">
                    </div>
                    <div class="form-group">
                        <label for="emergencyContactMobile">Mobile Number of Emergency Contact:</label>
                        <input type="text" id="emergencyContactMobile" name="Emergency Contact Mobile" required class="rounded-lg">
                    </div>
                </div>
            </div>

            <!-- Section 6: Declaration -->
            <div class="mb-8">
                <h2 class="section-title">Section 6: Declaration</h2>
                <div class="form-group mt-6">
                    <label class="flex items-center">
                        <input type="checkbox" id="declaration" name="Declaration Confirmation" required class="rounded mr-2">
                        I confirm that the information provided in this form is true and accurate to the best of my knowledge.
                    </label>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mt-6">
                    <div class="form-group">
                        <label for="signature">Signature (Type your full name):</label>
                        <input type="text" id="signature" name="Signature" required class="rounded-lg">
                    </div>
                    <div class="form-group">
                        <label for="declarationDate">Date:</label>
                        <input type="date" id="declarationDate" name="Declaration Date" required class="rounded-lg">
                    </div>
                </div>
            </div>

            <div class="text-center">
                <button type="submit" class="submit-button rounded-lg">Submit Form</button>
            </div>
        </form>
    </div>

    <script>
        // Function to show/hide visa-related fields
        function toggleVisaFields(show) {
            const visaFields = document.getElementById('visaFields');
            if (show) {
                visaFields.classList.remove('hidden');
                // Make fields required when visible
                document.getElementById('visaType').setAttribute('required', 'required');
                document.getElementById('visaExpiryDate').setAttribute('required', 'required');
            } else {
                visaFields.classList.add('hidden');
                // Remove required attribute when hidden
                document.getElementById('visaType').removeAttribute('required');
                document.getElementById('visaExpiryDate').removeAttribute('required');
            }
        }

        // Function to show/hide certificate upload fields (RSA/RCG)
        function toggleCertificateUpload(groupId, show) {
            const group = document.getElementById(groupId);
            if (show) {
                group.classList.remove('hidden');
            } else {
                group.classList.add('hidden');
                // Reset file input and display text when hidden
                const fileInput = group.querySelector('input[type="file"]');
                if (fileInput) {
                    fileInput.value = ''; // Clear selected file
                    const fileNameSpanId = fileInput.id.replace('Upload', 'FileName');
                    document.getElementById(fileNameSpanId).textContent = 'No file chosen';
                }
            }
        }

        // Function to display selected file name
        function displayFileName(inputId, spanId) {
            const input = document.getElementById(inputId);
            const span = document.getElementById(spanId);
            if (input.files.length > 0) {
                span.textContent = input.files[0].name;
            } else {
                span.textContent = 'No file chosen';
            }
        }

        // Function to show/hide superannuation fields
        function toggleSuperFundFields(hasExisting) {
            const superFundFields = document.getElementById('superFundFields');
            const defaultSuperInfo = document.getElementById('defaultSuperInfo');
            if (hasExisting) {
                superFundFields.classList.remove('hidden');
                defaultSuperInfo.classList.add('hidden');
                // Make fields required when visible
                document.getElementById('superFundName').setAttribute('required', 'required');
                document.getElementById('superFundABN').setAttribute('required', 'required');
                document.getElementById('superFundUSI').setAttribute('required', 'required');
                document.getElementById('memberNumber').setAttribute('required', 'required');
            } else {
                superFundFields.classList.add('hidden');
                defaultSuperInfo.classList.remove('hidden');
                // Remove required attribute when hidden
                document.getElementById('superFundName').removeAttribute('required');
                document.getElementById('superFundABN').removeAttribute('required');
                document.getElementById('superFundUSI').removeAttribute('required');
                document.getElementById('memberNumber').removeAttribute('required');
            }
        }

        // Initialize visibility of conditional fields on page load
        document.addEventListener('DOMContentLoaded', () => {
            toggleVisaFields(false);
            toggleCertificateUpload('rsaUploadGroup', false);
            toggleCertificateUpload('rcgUploadGroup', false);
            toggleSuperFundFields(false);
        });
    </script>
</body>
</html>
