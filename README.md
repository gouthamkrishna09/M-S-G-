# M-S-G-
Nfc landing page of msg's portfolio 
<!DOCTYPE html>
<html lang="en" class="dark">
	<head>
		<meta charset="UTF-8" />
		<meta name="viewport" content="width=device-width, initial-scale=1.0" />
		<title>M S GOUTHAMKRISHNA | NECT NFC Business Card </title>
		<!-- Tailwind CSS CDN -->
		<script src="https://cdn.tailwindcss.com"></script>
		<script>
			tailwind.config = {
			    darkMode: 'class',
			    theme: {
			        extend: {
			            colors: {
			                carddark: '#0f172a',
			                glassdark: 'rgba(30, 41, 59, 0.7)',
			                accent: '#6366f1',
			                accenthover: '#4f46e5'
			            },
			            fontFamily: {
			                sans: ['Inter', 'sans-serif']
			            }
			        }
			    }
			}
		</script>
		<!-- Google Fonts Inter -->
		<link
			href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap"
			rel="stylesheet"
		/>
		<!-- FontAwesome Icons -->
		<link
			rel="stylesheet"
			href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css"
		/>
		<style>
			body {
			    font-family: 'Inter', sans-serif;
			    background: linear-gradient(135deg, #090d16 0%, #1e1b4b 50%, #0f172a 100%);
			    min-height: 100vh;
			}
			.glass-card {
			    background: rgba(15, 23, 42, 0.75);
			    backdrop-filter: blur(16px);
			    -webkit-backdrop-filter: blur(16px);
			    border: 1px solid rgba(255, 255, 255, 0.1);
			}
			.glass-panel {
			    background: rgba(15, 23, 42, 0.85);
			    backdrop-filter: blur(20px);
			    -webkit-backdrop-filter: blur(20px);
			    border: 1px solid rgba(255, 255, 255, 0.1);
			}
			.glass-button {
			    background: rgba(30, 41, 59, 0.6);
			    backdrop-filter: blur(10px);
			    border: 1px solid rgba(255, 255, 255, 0.08);
			    transition: all 0.25s ease;
			}
			.glass-button:hover {
			    background: rgba(51, 65, 85, 0.8);
			    border-color: rgba(99, 102, 241, 0.4);
			    transform: translateY(-2px);
			    box-shadow: 0 10px 25px -5px rgba(99, 102, 241, 0.2);
			}
			.wallet-pass {
			    background: linear-gradient(135deg, #1c1c1e 0%, #2c2c2e 100%);
			    border-radius: 24px;
			    box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.7);
			}
			/* Custom Scrollbar for Editor Panel */
			::-webkit-scrollbar {
			    width: 6px;
			}
			::-webkit-scrollbar-track {
			    background: rgba(15, 23, 42, 0.5);
			}
			::-webkit-scrollbar-thumb {
			    background: rgba(99, 102, 241, 0.3);
			    border-radius: 4px;
			}
			::-webkit-scrollbar-thumb:hover {
			    background: rgba(99, 102, 241, 0.6);
			}
		</style>
	</head>
	<body class="text-slate-100 flex flex-col xl:flex-row min-h-screen">
		<!-- TOP / SIDEBAR CONTROLS (Template Editor) -->
		<aside
			id="editorSidebar"
			class="w-full xl:w-[440px] glass-panel border-b xl:border-b-0 xl:border-r border-slate-800 flex flex-col h-auto xl:h-screen sticky top-0 z-40 transition-all duration-300"
		>
			<!-- Sidebar Header -->
			<div
				class="p-5 border-b border-slate-800 flex items-center justify-between"
			>
				<div class="flex items-center gap-2.5">
					<div
						class="w-8 h-8 rounded-xl bg-indigo-600 flex items-center justify-center text-white font-bold text-sm shadow-md shadow-indigo-600/30"
					>
						<i class="fa-solid fa-wand-magic-sparkles text-xs"></i>
					</div>
					<div>
						<h2 class="font-bold text-sm text-white">
							Card Studio & Customizer
						</h2>
						<p class="text-[10px] text-slate-400">
							Personalize your NFC business card template
						</p>
					</div>
				</div>
				<div class="flex items-center gap-2">
					<button
						onclick="toggleEditorPanel()"
						class="xl:hidden w-8 h-8 rounded-lg bg-slate-800 flex items-center justify-center text-slate-300 hover:text-white"
						aria-label="Toggle Panel"
					>
						<i
							class="fa-solid fa-chevron-down text-xs"
							id="toggleIcon"
						></i>
					</button>
				</div>
			</div>

			<!-- Scrollable Form Inputs -->
			<div
				id="editorContent"
				class="p-5 space-y-5 overflow-y-auto flex-1 max-h-[calc(100vh-140px)]"
			>
				<!-- Quick Mode Toggle Bar -->
				<div
					class="bg-slate-900/80 p-1.5 rounded-2xl flex items-center gap-1 border border-slate-800"
				>
					<button
						onclick="setMode('preview')"
						id="modePreviewBtn"
						class="flex-1 py-2 text-xs font-medium rounded-xl transition bg-indigo-600 text-white shadow"
					>
						<i class="fa-solid fa-eye mr-1.5"></i> Live Preview
					</button>
					<button
						onclick="setMode('edit')"
						id="modeEditBtn"
						class="flex-1 py-2 text-xs font-medium rounded-xl transition text-slate-400 hover:text-white"
					>
						<i class="fa-solid fa-pen-to-square mr-1.5"></i> Edit
						Mode
					</button>
				</div>

				<!-- Section 1: Profile Info -->
				<div class="space-y-3">
					<h3
						class="text-xs font-bold uppercase tracking-wider text-indigo-400"
					>
						1. Personal Information
					</h3>

					<div>
						<label
							class="block text-[11px] text-slate-400 mb-1 font-medium"
							>Full Name</label
						>
						<input
							type="text"
							id="inputName"
							oninput="updateCard()"
							value="Alex Rivera"
							class="w-full bg-slate-900/90 border border-slate-700 rounded-xl px-3 py-2 text-xs text-white focus:outline-none focus:border-indigo-500"
						/>
					</div>

					<div class="grid grid-cols-2 gap-2">
						<div>
							<label
								class="block text-[11px] text-slate-400 mb-1 font-medium"
								>Job Title</label
							>
							<input
								type="text"
								id="inputTitle"
								oninput="updateCard()"
								value="Lead Product Designer"
								class="w-full bg-slate-900/90 border border-slate-700 rounded-xl px-3 py-2 text-xs text-white focus:outline-none focus:border-indigo-500"
							/>
						</div>
						<div>
							<label
								class="block text-[11px] text-slate-400 mb-1 font-medium"
								>Company</label
							>
							<input
								type="text"
								id="inputCompany"
								oninput="updateCard()"
								value="Nexus Innovate Corp."
								class="w-full bg-slate-900/90 border border-slate-700 rounded-xl px-3 py-2 text-xs text-white focus:outline-none focus:border-indigo-500"
							/>
						</div>
					</div>

					<div class="grid grid-cols-2 gap-2">
						<div>
							<label
								class="block text-[11px] text-slate-400 mb-1 font-medium"
								>Location</label
							>
							<input
								type="text"
								id="inputLocation"
								oninput="updateCard()"
								value="San Francisco, CA"
								class="w-full bg-slate-900/90 border border-slate-700 rounded-xl px-3 py-2 text-xs text-white focus:outline-none focus:border-indigo-500"
							/>
						</div>
						<div>
							<label
								class="block text-[11px] text-slate-400 mb-1 font-medium"
								>Avatar Image URL</label
							>
							<input
								type="text"
								id="inputAvatar"
								oninput="updateCard()"
								value="https://images.unsplash.com/photo-1534528741775-53994a69daeb?q=80&w=400&auto=format&fit=crop"
								class="w-full bg-slate-900/90 border border-slate-700 rounded-xl px-3 py-2 text-xs text-white focus:outline-none focus:border-indigo-500"
							/>
						</div>
					</div>

					<!-- Gallery / Cloud File Upload Option -->
					<div>
						<label class="block text-[11px] text-slate-400 mb-1 font-medium">Upload Avatar from Gallery / Cloud</label>
						<label class="w-full bg-slate-900/90 border border-slate-700 hover:border-indigo-500 rounded-xl px-3 py-2 text-xs text-slate-300 flex items-center justify-center gap-2 cursor-pointer transition">
							<i class="fa-solid fa-cloud-arrow-up text-indigo-400"></i>
							<span>Choose Image from Device</span>
							<input type="file" id="inputAvatarFile" accept="image/*" onchange="uploadAvatarFile(event)" class="hidden" />
						</label>
					</div>

					<div>
						<label
							class="block text-[11px] text-slate-400 mb-1 font-medium"
							>Professional Bio</label
						>
						<textarea
							id="inputBio"
							oninput="updateCard()"
							rows="2"
							class="w-full bg-slate-900/90 border border-slate-700 rounded-xl px-3 py-2 text-xs text-white focus:outline-none focus:border-indigo-500 resize-none"
						>
Crafting intuitive digital experiences and scalable design systems. Passionate about AI interfaces, mobile experiences, and modern web architecture.</textarea
						>
					</div>
				</div>

				<!-- Section 2: Direct Contact Channels -->
				<div class="space-y-3 pt-2 border-t border-slate-800">
					<h3
						class="text-xs font-bold uppercase tracking-wider text-indigo-400"
					>
						2. Direct Contact Channels
					</h3>

					<div class="grid grid-cols-2 gap-2">
						<div>
							<label
								class="block text-[11px] text-slate-400 mb-1 font-medium"
								>Phone Number</label
							>
							<input
								type="text"
								id="inputPhone"
								oninput="updateCard()"
								value="+15552345678"
								class="w-full bg-slate-900/90 border border-slate-700 rounded-xl px-3 py-2 text-xs text-white focus:outline-none focus:border-indigo-500"
							/>
						</div>
						<div>
							<label
								class="block text-[11px] text-slate-400 mb-1 font-medium"
								>Email Address</label
							>
							<input
								type="email"
								id="inputEmail"
								oninput="updateCard()"
								value="alex.rivera@nexusinnovate.io"
								class="w-full bg-slate-900/90 border border-slate-700 rounded-xl px-3 py-2 text-xs text-white focus:outline-none focus:border-indigo-500"
							/>
						</div>
					</div>

					<div class="grid grid-cols-2 gap-2">
						<div>
							<label
								class="block text-[11px] text-slate-400 mb-1 font-medium"
								>WhatsApp Number</label
							>
							<input
								type="text"
								id="inputWhatsapp"
								oninput="updateCard()"
								value="+15552345678"
								class="w-full bg-slate-900/90 border border-slate-700 rounded-xl px-3 py-2 text-xs text-white focus:outline-none focus:border-indigo-500"
							/>
						</div>
						<div>
							<label
								class="block text-[11px] text-slate-400 mb-1 font-medium"
								>SMS Number</label
							>
							<input
								type="text"
								id="inputSms"
								oninput="updateCard()"
								value="+15552345678"
								class="w-full bg-slate-900/90 border border-slate-700 rounded-xl px-3 py-2 text-xs text-white focus:outline-none focus:border-indigo-500"
							/>
						</div>
					</div>
				</div>

				<!-- Section 3: Custom Links Manager -->
				<div class="space-y-3 pt-2 border-t border-slate-800">
					<div class="flex items-center justify-between">
						<h3
							class="text-xs font-bold uppercase tracking-wider text-indigo-400"
						>
							3. Social & Portfolio Links
						</h3>
						<button
							onclick="addLinkField()"
							class="text-[11px] bg-indigo-600/20 hover:bg-indigo-600/40 text-indigo-300 px-2.5 py-1 rounded-lg transition flex items-center gap-1 font-medium"
						>
							<i class="fa-solid fa-plus text-[10px]"></i> Add
							Link
						</button>
					</div>

					<div id="linksEditorContainer" class="space-y-2">
						<!-- Dynamically populated via JS -->
					</div>
				</div>

				<!-- Action Buttons for Template -->
				<div class="pt-4 border-t border-slate-800 space-y-2.5">
					<button
						onclick="exportFullHTML()"
						class="w-full py-3 bg-indigo-600 hover:bg-indigo-500 text-white font-medium rounded-xl text-xs transition shadow-lg shadow-indigo-600/30 flex items-center justify-center gap-2"
					>
						<i class="fa-solid fa-code"></i> Export Custom HTML File
					</button>
					<button
						onclick="resetTemplateData()"
						class="w-full py-2.5 bg-slate-800 hover:bg-slate-700 text-slate-300 font-medium rounded-xl text-xs transition border border-slate-700 flex items-center justify-center gap-2"
					>
						<i class="fa-solid fa-rotate-left"></i> Reset to Default
					</button>
				</div>
			</div>
		</aside>

		<!-- MAIN PREVIEW STAGE CONTAINER -->
		<main
			class="flex-1 flex items-center justify-center p-4 sm:p-6 md:p-10 relative overflow-y-auto"
		>
			<!-- Live NFC Card Container -->
			<div
				id="previewCardElement"
				class="w-full max-w-md glass-card rounded-3xl shadow-2xl overflow-hidden relative my-auto transition-all duration-300"
			>
				<!-- Top Banner Accent & NFC Glow Indicator -->
				<div
					class="h-32 bg-gradient-to-r from-indigo-600 via-purple-600 to-pink-600 relative p-4 flex justify-between items-start"
				>
					<div
						class="absolute top-4 left-4 bg-black/35 backdrop-blur-md px-3 py-1 rounded-full text-xs font-medium text-white/90 flex items-center gap-1.5 border border-white/10"
					>
						<span
							class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"
						></span>
						NFC Active
					</div>
					<button
						onclick="openShareModal()"
						class="absolute top-4 right-4 w-9 h-9 bg-black/35 backdrop-blur-md rounded-full flex items-center justify-center text-white/90 hover:bg-black/55 transition border border-white/10"
						aria-label="Share Card"
					>
						<i class="fa-solid fa-share-nodes text-sm"></i>
					</button>
				</div>

				<!-- Profile Information Section -->
				<div
					class="px-6 pb-6 pt-0 relative flex flex-col items-center text-center"
				>
					<!-- Profile Avatar with Ring -->
					<div class="relative -mt-16 mb-4">
						<img
							id="cardAvatarImg"
							src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?q=80&w=400&auto=format&fit=crop"
							onerror="this.src='https://placehold.co/150x150/1e293b/ffffff?text=AR'"
							alt="Profile Picture"
							class="w-28 h-28 rounded-full object-cover border-4 border-slate-900 shadow-xl"
						/>
						<div
							class="absolute bottom-0 right-0 bg-indigo-600 text-white p-1.5 rounded-full border-2 border-slate-900 shadow"
							title="Verified Professional"
						>
							<i class="fa-solid fa-check text-xs"></i>
						</div>
					</div>

					<!-- Name, Title & Company -->
					<h1
						id="cardName"
						class="text-2xl font-bold tracking-tight text-white mb-1"
					>
						Alex Rivera
					</h1>
					<p
						id="cardTitle"
						class="text-indigo-400 font-medium text-sm mb-1"
					>
						Lead Product Designer
					</p>
					<p
						class="text-slate-400 text-xs mb-4 flex items-center gap-1.5"
					>
						<i class="fa-solid fa-building text-slate-500"></i>
						<span id="cardCompany">Nexus Innovate Corp.</span>
						<span class="text-slate-600">•</span>
						<i class="fa-solid fa-location-dot text-slate-500"></i>
						<span id="cardLocation">San Francisco, CA</span>
					</p>

					<!-- Bio -->
					<p
						id="cardBio"
						class="text-slate-300 text-xs leading-relaxed px-2 mb-6"
					>
						Crafting intuitive digital experiences and scalable
						design systems. Passionate about AI interfaces, mobile
						experiences, and modern web architecture.
					</p>

					<!-- Primary Actions: Save Contact & Apple Wallet -->
					<div class="grid grid-cols-2 gap-3 w-full mb-6">
						<button
							onclick="downloadVCard()"
							class="flex items-center justify-center gap-2 bg-indigo-600 hover:bg-indigo-500 text-white font-medium py-3 px-4 rounded-xl text-xs transition shadow-lg shadow-indigo-600/30"
						>
							<i class="fa-solid fa-user-plus"></i>
							Save Contact
						</button>
						<button
							onclick="openWalletModal()"
							class="flex items-center justify-center gap-2 bg-slate-800 hover:bg-slate-700 text-white font-medium py-3 px-4 rounded-xl text-xs transition border border-slate-700"
						>
							<i class="fa-solid fa-wallet text-amber-400"></i>
							Apple Wallet
						</button>
					</div>

					<!-- Quick Action Icons Row (Call, Email, WhatsApp, SMS) -->
					<div
						class="flex items-center justify-center gap-4 w-full mb-6 pb-6 border-b border-slate-800"
					>
						<a
							id="actionPhone"
							href="tel:+15552345678"
							class="w-12 h-12 rounded-2xl glass-button flex flex-col items-center justify-center text-indigo-400 hover:text-white"
							title="Call"
						>
							<i class="fa-solid fa-phone text-base"></i>
						</a>
						<a
							id="actionEmail"
							href="mailto:alex.rivera@nexusinnovate.io"
							class="w-12 h-12 rounded-2xl glass-button flex flex-col items-center justify-center text-indigo-400 hover:text-white"
							title="Email"
						>
							<i class="fa-solid fa-envelope text-base"></i>
						</a>
						<a
							id="actionWhatsapp"
							href="https://wa.me/15552345678"
							target="_blank"
							rel="noopener noreferrer"
							class="w-12 h-12 rounded-2xl glass-button flex flex-col items-center justify-center text-emerald-400 hover:text-white"
							title="WhatsApp"
						>
							<i class="fa-brands fa-whatsapp text-lg"></i>
						</a>
						<a
							id="actionSms"
							href="sms:+15552345678"
							class="w-12 h-12 rounded-2xl glass-button flex flex-col items-center justify-center text-sky-400 hover:text-white"
							title="Text Message"
						>
							<i class="fa-solid fa-comment-sms text-base"></i>
						</a>
					</div>

					<!-- Dynamic Links List Section -->
					<div id="cardLinksContainer" class="w-full space-y-3 mb-6">
						<!-- Populated dynamically -->
					</div>

					<!-- Footer Branding / Exchange Button -->
					<button
						onclick="triggerExchangePrompt()"
						class="w-full py-3 rounded-xl border border-dashed border-slate-700 hover:border-indigo-500 text-slate-400 hover:text-indigo-300 text-xs font-medium transition flex items-center justify-center gap-2"
					>
						<i class="fa-solid fa-address-card"></i>
						Exchange Contact Info Back
					</button>
					<p class="text-[10px] text-slate-500 mt-4">
						Powered by Nect NFC by otronics
					</p>
				</div>
			</div>
		</main>

		<!-- Apple Wallet Modal Simulation -->
		<div
			id="walletModal"
			class="fixed inset-0 bg-black/80 backdrop-blur-sm z-50 flex items-center justify-center p-4 hidden opacity-0 transition-opacity duration-300"
		>
			<div
				class="wallet-pass w-full max-w-sm p-6 text-white relative transform scale-95 transition-transform duration-300"
				id="walletModalContent"
			>
				<!-- Close Button -->
				<button
					onclick="closeWalletModal()"
					class="absolute top-4 right-4 w-8 h-8 rounded-full bg-white/10 flex items-center justify-center text-white/70 hover:text-white hover:bg-white/20 transition"
				>
					<i class="fa-solid fa-xmark text-sm"></i>
				</button>

				<!-- Pass Header -->
				<div class="flex items-center gap-3 mb-6">
					<div
						id="walletInitials"
						class="w-10 h-10 rounded-xl bg-indigo-600 flex items-center justify-center font-bold text-lg shadow-md"
					>
						AR
					</div>
					<div>
						<h3 id="walletCompany" class="font-bold text-sm">
							Nexus Innovate
						</h3>
						<p
							class="text-[10px] text-slate-400 uppercase tracking-wider"
						>
							Digital Business Pass
						</p>
					</div>
				</div>

				<!-- Pass QR Code Container -->
				<div
					class="bg-white p-4 rounded-2xl flex flex-col items-center justify-center mb-6 shadow-inner"
				>
					<!-- Inline SVG QR Code simulation -->
					<svg
						class="w-48 h-48"
						viewBox="0 0 24 24"
						fill="none"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path d="M2 2H10V10H2V2Z" fill="#0f172a" />
						<path d="M14 2H22V10H14V2Z" fill="#0f172a" />
						<path d="M2 14H10V22H2V14Z" fill="#0f172a" />
						<rect x="4" y="4" width="4" height="4" fill="white" />
						<rect x="16" y="4" width="4" height="4" fill="white" />
						<rect x="4" y="16" width="4" height="4" fill="white" />
						<rect
							x="14"
							y="14"
							width="2"
							height="2"
							fill="#0f172a"
						/>
						<rect
							x="18"
							y="18"
							width="4"
							height="4"
							fill="#0f172a"
						/>
						<rect
							x="18"
							y="14"
							width="2"
							height="2"
							fill="#0f172a"
						/>
						<rect
							x="14"
							y="18"
							width="2"
							height="2"
							fill="#0f172a"
						/>
						<path d="M12 2H13V6H12V2Z" fill="#0f172a" />
						<path d="M12 8H13V12H12V8Z" fill="#0f172a" />
						<path d="M8 12H12V13H8V12Z" fill="#0f172a" />
						<path d="M2 12H6V13H2V12Z" fill="#0f172a" />
					</svg>
					<p class="text-[10px] text-slate-500 mt-2 font-mono">
						Scan to instantly connect
					</p>
				</div>

				<!-- Pass Meta Details -->
				<div
					class="space-y-2 mb-6 text-xs bg-white/5 p-3 rounded-xl border border-white/5"
				>
					<div class="flex justify-between">
						<span class="text-slate-400">Cardholder</span>
						<span id="walletName" class="font-medium text-white"
							>Alex Rivera</span
						>
					</div>
					<div class="flex justify-between">
						<span class="text-slate-400">Title</span>
						<span id="walletTitle" class="font-medium text-white"
							>Lead Product Designer</span
						>
					</div>
					<div class="flex justify-between">
						<span class="text-slate-400">Valid Through</span>
						<span class="font-medium text-emerald-400"
							>Unlimited</span
						>
					</div>
				</div>

				<!-- Action Button -->
				<button
					onclick="simulateAddToWallet()"
					class="w-full py-3.5 bg-black hover:bg-zinc-900 border border-white/20 rounded-xl font-semibold text-xs flex items-center justify-center gap-2 transition shadow-lg"
				>
					<i class="fa-brands fa-apple text-base"></i>
					Add to Apple Wallet
				</button>
			</div>
		</div>

		<!-- Share Modal -->
		<div
			id="shareModal"
			class="fixed inset-0 bg-black/80 backdrop-blur-sm z-50 flex items-center justify-center p-4 hidden opacity-0 transition-opacity duration-300"
		>
			<div
				class="glass-card w-full max-w-xs p-6 rounded-3xl text-center relative transform scale-95 transition-transform duration-300"
				id="shareModalContent"
			>
				<button
					onclick="closeShareModal()"
					class="absolute top-4 right-4 w-8 h-8 rounded-full bg-white/10 flex items-center justify-center text-white/70 hover:text-white transition"
				>
					<i class="fa-solid fa-xmark text-sm"></i>
				</button>
				<h3 class="font-bold text-base mb-1">Share Business Card</h3>
				<p class="text-xs text-slate-400 mb-6">
					Send this NFC card to colleagues or friends
				</p>

				<div class="grid grid-cols-3 gap-3 mb-6">
					<button
						onclick="copyCardLink()"
						class="flex flex-col items-center gap-2 p-3 rounded-2xl glass-button hover:bg-indigo-600/20"
					>
						<i class="fa-solid fa-link text-indigo-400 text-lg"></i>
						<span class="text-[10px] text-slate-300"
							>Copy Link</span
						>
					</button>
					<a
						id="shareEmailBtn"
						href="#"
						class="flex flex-col items-center gap-2 p-3 rounded-2xl glass-button hover:bg-indigo-600/20"
					>
						<i
							class="fa-solid fa-envelope text-blue-400 text-lg"
						></i>
						<span class="text-[10px] text-slate-300">Email</span>
					</a>
					<a
						id="shareWhatsappBtn"
						href="#"
						target="_blank"
						rel="noopener noreferrer"
						class="flex flex-col items-center gap-2 p-3 rounded-2xl glass-button hover:bg-indigo-600/20"
					>
						<i
							class="fa-brands fa-whatsapp text-emerald-400 text-lg"
						></i>
						<span class="text-[10px] text-slate-300">WhatsApp</span>
					</a>
				</div>

				<div
					id="copyToast"
					class="hidden text-[11px] text-emerald-400 font-medium bg-emerald-500/10 py-1.5 rounded-lg border border-emerald-500/20"
				>
					Link copied to clipboard!
				</div>
			</div>
		</div>

		<!-- Exchange Contact Form Modal -->
		<div
			id="exchangeModal"
			class="fixed inset-0 bg-black/80 backdrop-blur-sm z-50 flex items-center justify-center p-4 hidden opacity-0 transition-opacity duration-300"
		>
			<div
				class="glass-card w-full max-w-sm p-6 rounded-3xl relative transform scale-95 transition-transform duration-300"
				id="exchangeModalContent"
			>
				<button
					onclick="closeExchangeModal()"
					class="absolute top-4 right-4 w-8 h-8 rounded-full bg-white/10 flex items-center justify-center text-white/70 hover:text-white transition"
				>
					<i class="fa-solid fa-xmark text-sm"></i>
				</button>
				<h3 class="font-bold text-base mb-1 text-center">
					Exchange Contact Info
				</h3>
				<p
					id="exchangeSubtitle"
					class="text-xs text-slate-400 mb-4 text-center"
				>
					Send your details directly
				</p>

				<form onsubmit="submitExchange(event)" class="space-y-3">
					<div>
						<label
							class="block text-[11px] text-slate-400 mb-1 font-medium"
							>Your Name</label
						>
						<input
							type="text"
							required
							placeholder="Jane Doe"
							class="w-full bg-slate-900/80 border border-slate-700 rounded-xl px-3 py-2 text-xs text-white focus:outline-none focus:border-indigo-500"
						/>
					</div>
					<div>
						<label
							class="block text-[11px] text-slate-400 mb-1 font-medium"
							>Your Email or Phone</label
						>
						<input
							type="text"
							required
							placeholder="jane@company.com"
							class="w-full bg-slate-900/80 border border-slate-700 rounded-xl px-3 py-2 text-xs text-white focus:outline-none focus:border-indigo-500"
						/>
					</div>
					<button
						type="submit"
						class="w-full py-3 bg-indigo-600 hover:bg-indigo-500 text-white font-medium rounded-xl text-xs transition shadow-lg shadow-indigo-600/30 mt-2"
					>
						Send My Info
					</button>
				</form>
				<div id="exchangeSuccess" class="hidden text-center py-6">
					<div
						class="w-12 h-12 bg-emerald-500/20 text-emerald-400 rounded-full flex items-center justify-center mx-auto mb-3 text-xl"
					>
						<i class="fa-solid fa-check"></i>
					</div>
					<h4 class="font-bold text-sm text-white mb-1">
						Sent Successfully!
					</h4>
					<p class="text-xs text-slate-400">
						Details received instantly.
					</p>
				</div>
			</div>
		</div>

		<!-- Notification Toast Message Box -->
		<div
			id="notificationToast"
			class="fixed bottom-6 left-1/2 -translate-x-1/2 bg-slate-900/95 border border-indigo-500/30 text-white text-xs px-4 py-3 rounded-2xl shadow-2xl z-50 flex items-center gap-3 transform translate-y-20 opacity-0 transition-all duration-300"
		>
			<div id="toastIcon" class="text-indigo-400 text-sm">
				<i class="fa-solid fa-circle-check"></i>
			</div>
			<span id="toastMessage">Notification message</span>
		</div>

		<!-- Interactive Customizer & App Logic -->
		<script>
			        // Default Template State / Links
			        let cardData = {
			            name: "Alex Rivera",
			            title: "Lead Product Designer",
			            company: "Nexus Innovate Corp.",
			            location: "San Francisco, CA",
			            avatar: "https://images.unsplash.com/photo-1534528741775-53994a69daeb?q=80&w=400&auto=format&fit=crop",
			            bio: "Crafting intuitive digital experiences and scalable design systems. Passionate about AI interfaces, mobile experiences, and modern web architecture.",
			            phone: "+15552345678",
			            email: "alex.rivera@nexusinnovate.io",
			            whatsapp: "+15552345678",
			            sms: "+15552345678",
			            links: [
			                { label: "Portfolio Website", subtitle: "alexrivera.design", url: "https://alexrivera.design", icon: "fa-solid fa-globe", color: "indigo" },
			                { label: "LinkedIn Profile", subtitle: "in/alexrivera-design", url: "https://linkedin.com", icon: "fa-brands fa-linkedin-in", color: "blue" },
			                { label: "X (Twitter)", subtitle: "@ariveradesign", url: "https://twitter.com", icon: "fa-brands fa-x-twitter", color: "sky" },
			                { label: "GitHub Repository", subtitle: "github.com/alexrivera", url: "https://github.com", icon: "fa-brands fa-github", color: "purple" }
			            ]
			        };

			        // Initialize App on Load
			        window.addEventListener('DOMContentLoaded', () => {
			            renderLinksEditor();
			            updateCard();
			        });

			        // Toggle Preview / Edit Mode for responsive sidebar
			        function setMode(mode) {
			            const previewBtn = document.getElementById('modePreviewBtn');
			            const editBtn = document.getElementById('modeEditBtn');
			            if (mode === 'preview') {
			                previewBtn.className = "flex-1 py-2 text-xs font-medium rounded-xl transition bg-indigo-600 text-white shadow";
			                editBtn.className = "flex-1 py-2 text-xs font-medium rounded-xl transition text-slate-400 hover:text-white";
			                showToast('Switched to Live Preview Mode', 'success');
			            } else {
			                editBtn.className = "flex-1 py-2 text-xs font-medium rounded-xl transition bg-indigo-600 text-white shadow";
			                previewBtn.className = "flex-1 py-2 text-xs font-medium rounded-xl transition text-slate-400 hover:text-white";
			                showToast('Switched to Edit Mode', 'success');
			            }
			        }

			        function toggleEditorPanel() {
			            const content = document.getElementById('editorContent');
			            const icon = document.getElementById('toggleIcon');
			            content.classList.toggle('hidden');
			            icon.classList.toggle('rotate-180');
			        }

			        // Render Dynamic Links Inputs in Sidebar
			        function renderLinksEditor() {
			            const container = document.getElementById('linksEditorContainer');
			            container.innerHTML = '';

			            cardData.links.forEach((link, idx) => {
			                const item = document.createElement('div');
			                item.className = "bg-slate-900/60 p-3 rounded-xl border border-slate-800 space-y-2 relative group";
			                item.innerHTML = `
			                    <div class="flex items-center justify-between">
			                        <span class="text-[10px] font-bold text-indigo-400 uppercase">Link #${idx + 1}</span>
			                        <button onclick="removeLink(${idx})" class="text-slate-500 hover:text-rose-400 transition p-1" title="Delete Link">
			                            <i class="fa-solid fa-trash text-xs"></i>
			                        </button>
			                    </div>
			                    <div class="grid grid-cols-2 gap-2">
			                        <input type="text" placeholder="Title (e.g. Portfolio)" value="${link.label}" oninput="updateLinkData(${idx}, 'label', this.value)" class="bg-slate-900 border border-slate-700 rounded-lg px-2.5 py-1.5 text-[11px] text-white focus:outline-none focus:border-indigo-500">
			                        <input type="text" placeholder="Subtitle (e.g. site.com)" value="${link.subtitle}" oninput="updateLinkData(${idx}, 'subtitle', this.value)" class="bg-slate-900 border border-slate-700 rounded-lg px-2.5 py-1.5 text-[11px] text-white focus:outline-none focus:border-indigo-500">
			                    </div>
			                    <div class="grid grid-cols-3 gap-2">
			                        <input type="text" placeholder="https://..." value="${link.url}" oninput="updateLinkData(${idx}, 'url', this.value)" class="col-span-2 bg-slate-900 border border-slate-700 rounded-lg px-2.5 py-1.5 text-[11px] text-white focus:outline-none focus:border-indigo-500">
			                        <select oninput="updateLinkData(${idx}, 'color', this.value)" class="bg-slate-900 border border-slate-700 rounded-lg px-2 py-1.5 text-[11px] text-white focus:outline-none focus:border-indigo-500">
			                            <option value="indigo" ${link.color==='indigo'?'selected':''}>Indigo</option>
			                            <option value="blue" ${link.color==='blue'?'selected':''}>Blue</option>
			                            <option value="sky" ${link.color==='sky'?'selected':''}>Sky</option>
			                            <option value="purple" ${link.color==='purple'?'selected':''}>Purple</option>
			                            <option value="emerald" ${link.color==='emerald'?'selected':''}>Emerald</option>
			                        </select>
			                    </div>
			                `;
			                container.appendChild(item);
			            });
			        }

			        function addLinkField() {
			            cardData.links.push({
			                label: "New Link",
			                subtitle: "example.com",
			                url: "https://example.com",
			                icon: "fa-solid fa-link",
			                color: "indigo"
			            });
			            renderLinksEditor();
			            updateCard();
			        }

			        function removeLink(idx) {
			            cardData.links.splice(idx, 1);
			            renderLinksEditor();
			            updateCard();
			        }

			        function updateLinkData(idx, field, val) {
			            cardData.links[idx][field] = val;
			            if (field === 'color') {
			                const colorsMap = {
			                    indigo: 'fa-solid fa-globe',
			                    blue: 'fa-brands fa-linkedin-in',
			                    sky: 'fa-brands fa-x-twitter',
			                    purple: 'fa-brands fa-github',
			                    emerald: 'fa-solid fa-star'
			                };
			                cardData.links[idx].icon = colorsMap[val] || 'fa-solid fa-link';
			            }
			            updateCard();
			        }

			        // Handle Gallery / Cloud File Upload
			        function uploadAvatarFile(event) {
			            const file = event.target.files[0];
			            if (file) {
			                const reader = new FileReader();
			                reader.onload = function(e) {
			                    cardData.avatar = e.target.result;
			                    document.getElementById('inputAvatar').value = e.target.result;
			                    updateCard();
			                    showToast('Profile picture loaded from gallery successfully!', 'success');
			                };
			                reader.readAsDataURL(file);
			            }
			        }

			        // Real-Time Live Update Function
			        function updateCard() {
			            // Read form inputs into cardData state
			            cardData.name = document.getElementById('inputName').value;
			            cardData.title = document.getElementById('inputTitle').value;
			            cardData.company = document.getElementById('inputCompany').value;
			            cardData.location = document.getElementById('inputLocation').value;
			            cardData.avatar = document.getElementById('inputAvatar').value;
			            cardData.bio = document.getElementById('inputBio').value;
			            cardData.phone = document.getElementById('inputPhone').value;
			            cardData.email = document.getElementById('inputEmail').value;
			            cardData.whatsapp = document.getElementById('inputWhatsapp').value;
			            cardData.sms = document.getElementById('inputSms').value;

			            // Update DOM Elements in Live Preview
			            document.getElementById('cardName').textContent = cardData.name;
			            document.getElementById('cardTitle').textContent = cardData.title;
			            document.getElementById('cardCompany').textContent = cardData.company;
			            document.getElementById('cardLocation').textContent = cardData.location;
			            document.getElementById('cardAvatarImg').src = cardData.avatar;
			            document.getElementById('cardBio').textContent = cardData.bio;

			            // Direct actions
			            document.getElementById('actionPhone').href = `tel:${cardData.phone}`;
			            document.getElementById('actionEmail').href = `mailto:${cardData.email}`;
			            document.getElementById('actionWhatsapp').href = `https://wa.me/${cardData.whatsapp.replace(/[^0-9]/g, '')}`;
			            document.getElementById('actionSms').href = `sms:${cardData.sms}`;

			            // Apple wallet modal fields
			            document.getElementById('walletName').textContent = cardData.name;
			            document.getElementById('walletTitle').textContent = cardData.title;
			            document.getElementById('walletCompany').textContent = cardData.company;

			            // Generate Initials for Wallet
			            const initials = cardData.name.split(' ').map(n => n[0]).join('').substring(0, 2).toUpperCase() || 'AR';
			            document.getElementById('walletInitials').textContent = initials;

			            // Render Links list in Preview
			            const linksContainer = document.getElementById('cardLinksContainer');
			            linksContainer.innerHTML = '';

			            cardData.links.forEach(link => {
			                const a = document.createElement('a');
			                a.href = link.url;
			                a.target = "_blank";
			                a.rel = "noopener noreferrer";
			                a.className = "glass-button w-full p-3.5 rounded-2xl flex items-center justify-between group";

			                const colorBg = {
			                    indigo: 'bg-indigo-500/10 text-indigo-400 group-hover:bg-indigo-500',
			                    blue: 'bg-blue-500/10 text-blue-400 group-hover:bg-blue-600',
			                    sky: 'bg-sky-500/10 text-sky-400 group-hover:bg-sky-500',
			                    purple: 'bg-purple-500/10 text-purple-400 group-hover:bg-purple-600',
			                    emerald: 'bg-emerald-500/10 text-emerald-400 group-hover:bg-emerald-600'
			                }[link.color] || 'bg-indigo-500/10 text-indigo-400 group-hover:bg-indigo-500';

			                const arrowColor = {
			                    indigo: 'group-hover:text-indigo-400',
			                    blue: 'group-hover:text-blue-400',
			                    sky: 'group-hover:text-sky-400',
			                    purple: 'group-hover:text-purple-400',
			                    emerald: 'group-hover:text-emerald-400'
			                }[link.color] || 'group-hover:text-indigo-400';

			                a.innerHTML = `
			                    <div class="flex items-center gap-3">
			                        <div class="w-9 h-9 rounded-xl ${colorBg} group-hover:text-white flex items-center justify-center transition">
			                            <i class="${link.icon} text-sm"></i>
			                        </div>
			                        <div class="text-left">
			                            <h4 class="text-xs font-semibold text-white">${link.label}</h4>
			                            <p class="text-[10px] text-slate-400">${link.subtitle}</p>
			                        </div>
			                    </div>
			                    <i class="fa-solid fa-arrow-up-right-from-square text-xs text-slate-500 ${arrowColor} transition"></i>
			                `;
			                linksContainer.appendChild(a);
			            });

			            // Share buttons
			            document.getElementById('shareEmailBtn').href = `mailto:?subject=${encodeURIComponent(cardData.name + "'s Digital Card")}&body=${encodeURIComponent("Check out digital business card: " + window.location.href)}`;
			            document.getElementById('shareWhatsappBtn').href = `https://api.whatsapp.com/send?text=${encodeURIComponent("Check out " + cardData.name + "'s digital business card!")}`;
			            document.getElementById('exchangeSubtitle').textContent = `Send your details directly to ${cardData.name}`;
			        }

			        // vCard Download Generator
			        function downloadVCard() {
			            const vcardData = `BEGIN:VCARD
			VERSION:3.0
			FN:${cardData.name}
			N:${cardData.name.split(' ').reverse().join(';')};;;
			TITLE:${cardData.title}
			ORG:${cardData.company}
			TEL:${cardData.phone}
			EMAIL:${cardData.email}
			URL:${cardData.links[0]?.url || ''}
			NOTE:Digital NFC Business Card - ${cardData.company}
			END:VCARD`;

			            const blob = new Blob([vcardData], { type: 'text/vcard;charset=utf-8;' });
			            const url = URL.createObjectURL(blob);
			            const link = document.createElement('a');
			            link.href = url;
			            link.setAttribute('download', `${cardData.name.replace(/\s+/g, '_')}.vcf`);
			            document.body.appendChild(link);
			            link.click();
			            document.body.removeChild(link);

			            showToast('vCard contact file downloaded!', 'success');
			        }

			        // Apple Wallet Modal Control
			        function openWalletModal() {
			            const modal = document.getElementById('walletModal');
			            const content = document.getElementById('walletModalContent');
			            modal.classList.remove('hidden');
			            setTimeout(() => {
			                modal.classList.remove('opacity-0');
			                content.classList.remove('scale-95');
			                content.classList.add('scale-100');
			            }, 10);
			        }

			        function closeWalletModal() {
			            const modal = document.getElementById('walletModal');
			            const content = document.getElementById('walletModalContent');
			            modal.classList.add('opacity-0');
			            content.classList.remove('scale-100');
			            content.classList.add('scale-95');
			            setTimeout(() => { modal.classList.add('hidden'); }, 300);
			        }

			        function simulateAddToWallet() {
			            closeWalletModal();
			            showToast('Pass added to Apple Wallet successfully!', 'wallet');
			        }

			        // Share Modal Control
			        function openShareModal() {
			            const modal = document.getElementById('shareModal');
			            const content = document.getElementById('shareModalContent');
			            modal.classList.remove('hidden');
			            setTimeout(() => {
			                modal.classList.remove('opacity-0');
			                content.classList.remove('scale-95');
			                content.classList.add('scale-100');
			            }, 10);
			        }

			        function closeShareModal() {
			            const modal = document.getElementById('shareModal');
			            const content = document.getElementById('shareModalContent');
			            modal.classList.add('opacity-0');
			            content.classList.remove('scale-100');
			            content.classList.add('scale-95');
			            setTimeout(() => { modal.classList.add('hidden'); }, 300);
			        }

			        function copyCardLink() {
			            const dummyUrl = window.location.href;
			            if (navigator.clipboard && navigator.clipboard.writeText) {
			                navigator.clipboard.writeText(dummyUrl).then(() => {
			                    document.getElementById('copyToast').classList.remove('hidden');
			                    setTimeout(() => document.getElementById('copyToast').classList.add('hidden'), 2500);
			                });
			            } else {
			                const textArea = document.createElement("textarea");
			                textArea.value = dummyUrl;
			                document.body.appendChild(textArea);
			                textArea.select();
			                try {
			                    document.execCommand('copy');
			                    document.getElementById('copyToast').classList.remove('hidden');
			                    setTimeout(() => document.getElementById('copyToast').classList.add('hidden'), 2500);
			                } catch (err) {}
			                document.body.removeChild(textArea);
			            }
			        }

			        // Exchange Contact Modal Control
			        function triggerExchangePrompt() {
			            const modal = document.getElementById('exchangeModal');
			            const content = document.getElementById('exchangeModalContent');
			            modal.classList.remove('hidden');
			            setTimeout(() => {
			                modal.classList.remove('opacity-0');
			                content.classList.remove('scale-95');
			                content.classList.add('scale-100');
			            }, 10);
			        }

			        function closeExchangeModal() {
			            const modal = document.getElementById('exchangeModal');
			            const content = document.getElementById('exchangeModalContent');
			            modal.classList.add('opacity-0');
			            setTimeout(() => {
			                modal.classList.add('hidden');
			                document.getElementById('exchangeSuccess').classList.add('hidden');
			                document.querySelector('#exchangeModal form').reset();
			                document.querySelector('#exchangeModal form').classList.remove('hidden');
			            }, 300);
			        }

			        function submitExchange(e) {
			            e.preventDefault();
			            document.querySelector('#exchangeModal form').classList.add('hidden');
			            document.getElementById('exchangeSuccess').classList.remove('hidden');
			            setTimeout(() => {
			                closeExchangeModal();
			                showToast(`Contact shared successfully with ${cardData.name}!`, 'success');
			            }, 2000);
			        }

			        // Export Full Customized HTML File
			        function exportFullHTML() {
			            const htmlContent = document.documentElement.outerHTML;
			            const blob = new Blob([htmlContent], { type: 'text/html;charset=utf-8;' });
			            const url = URL.createObjectURL(blob);
			            const link = document.createElement('a');
			            link.href = url;
			            link.setAttribute('download', `${cardData.name.replace(/\s+/g, '_')}_Digital_Card.html`);
			            document.body.appendChild(link);
			            link.click();
			            document.body.removeChild(link);
			            showToast('Customized HTML template exported successfully!', 'success');
			        }

			        function resetTemplateData() {
			            if (confirm('Reset all details to default template values?')) {
			                document.getElementById('inputName').value = "Alex Rivera";
			                document.getElementById('inputTitle').value = "Lead Product Designer";
			                document.getElementById('inputCompany').value = "Nexus Innovate Corp.";
			                document.getElementById('inputLocation').value = "San Francisco, CA";
			                document.getElementById('inputAvatar').value = "https://images.unsplash.com/photo-1534528741775-53994a69daeb?q=80&w=400&auto=format&fit=crop";
			                document.getElementById('inputBio').value = "Crafting intuitive digital experiences and scalable design systems. Passionate about AI interfaces, mobile experiences, and modern web architecture.";
			                document.getElementById('inputPhone').value = "+15552345678";
			                document.getElementById('inputEmail').value = "alex.rivera@nexusinnovate.io";
			                document.getElementById('inputWhatsapp').value = "+15552345678";
			                document.getElementById('inputSms').value = "+15552345678";
			                cardData.links = [
			                    { label: "Portfolio Website", subtitle: "alexrivera.design", url: "https://alexrivera.design", icon: "fa-solid fa-globe", color: "indigo" },
			                    { label: "LinkedIn Profile", subtitle: "in/alexrivera-design", url: "https://linkedin.com", icon: "fa-brands fa-linkedin-in", color: "blue" },
			                    { label: "X (Twitter)", subtitle: "@ariveradesign", url: "https://twitter.com", icon: "fa-brands fa-x-twitter", color: "sky" },
			                    { label: "GitHub Repository", subtitle: "github.com/alexrivera", url: "https://github.com", icon: "fa-brands fa-github", color: "purple" }
			                ];
			                renderLinksEditor();
			                updateCard();
			                showToast('Template reset to default values', 'success');
			            }
			        }

			        // Toast Notification Helper
			        function showToast(message, type = 'success') {
			            const toast = document.getElementById('notificationToast');
			            const msgEl = document.getElementById('toastMessage');
			            const iconEl = document.getElementById('toastIcon');

			            msgEl.textContent = message;
			            if (type === 'wallet') {
			                iconEl.innerHTML = '<i class="fa-brands fa-apple text-amber-400 text-base"></i>';
			            } else {
			                iconEl.innerHTML = '<i class="fa-solid fa-circle-check text-emerald-400 text-base"></i>';
			            }

			            toast.classList.remove('translate-y-20', 'opacity-0');
			            toast.classList.add('translate-y-0', 'opacity-100');

			            setTimeout(() => {
			                toast.classList.remove('translate-y-0', 'opacity-100');
			                toast.classList.add('translate-y-20', 'opacity-0');
			            }, 3500);
			        }
		</script>
	</body>
</html>