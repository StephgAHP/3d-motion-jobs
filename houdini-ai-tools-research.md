# AI Tools & Workflows for Houdini Specialists

Research compiled April 2026. Focused on currently available, practical tools.

---

## 1. AI/ML Features Built Into Houdini

### Houdini 21 Native ML Tools (Released August 2025)

SideFX shipped the largest number of ML-based tools in any Houdini release to date. These are built directly into the software.

**ML Deformer**
- Trains a neural network to replicate full CFX (cloth/flesh/muscle) simulations in real time
- Replaces slow per-frame simulation with fast inference, dramatically speeding up playback
- Uses 128 PCA coefficients, reducing neural network outputs from 150,000 to 128
- Works in both SOPs and APEX rigs via "ML Deform SOP" and "APEX Add ML Deformer SOP"
- Can be built entirely inside Houdini with no external coding
- URL: https://www.sidefx.com/contentlibrary/ml-deformer/

**ML Groom Deformer**
- Predicts how a groom (hair/fur) should deform around a character mesh based on rig positions
- Uses ML SOP/TOP nodes to build data generation and training pipelines inside Houdini without writing code
- URL: https://www.sidefx.com/contentlibrary/ml-groom-deformer/

**ML Volume Upres**
- Upscales pyro (fire/smoke) simulations without altering large-scale shapes
- Run a low-res sim, then ML upscales to high-res detail. Massive time savings.

**Neural Point Surface**
- Converts point clouds into meshes using pre-trained models
- Embedded in Particle Fluid Surface and MPM Surface nodes
- Different pre-trained models available based on surface characteristics (splashy water vs smooth surfaces etc.)

**ML Style Transfer**
- Apply artistic styles to renders/images using neural networks within Copernicus

**ONNX Runtime Integration**
- Houdini supports the ONNX format natively, allowing models trained in PyTorch or TensorFlow to be deployed inside Houdini
- Build custom ML filters in Copernicus using the ONNX engine

**ML Training TOPs (PDG)**
- ML Train Regression TOP node for training models inside Houdini's task-based pipeline
- Full pipeline: generate data > preprocess > train > export > deploy, all within Houdini

**Pricing**: Included with all Houdini licenses. Houdini Indie is $269-299/year (revenue cap $100K).

### Copernicus (Image Processing Framework)

- Production-ready 2D/3D GPU image processing framework (new in H20.5, mature in H21)
- Supports OpenFX standard tools and ONNX-based ML custom filters
- New in H21: sparse GPU Pyro FX solver, reaction diffusion, texture baking, live video tool, grunge map library, material presets
- Can run Stable Diffusion and other generative AI models via ONNX integration
- URL: https://www.sidefx.com/products/whats-new-in-h205/copernicus/

### APEX Rigging System

- Not AI per se, but the procedural rigging system that ML deformers plug into
- Auto-rig components (limb, hand, foot, neck, spine, scapula, ulna) with drag-and-drop viewport builder
- Rig transfer between characters with different joint hierarchies
- "Otto": production-ready human with muscle and tissue simulation out of the box
- URL: https://www.sidefx.com/products/whats-new-in-h20/animation/

### Otis Solver

- GPU-accelerated organic tissue simulation engine
- FEM-grade accuracy with real-time APEX animation
- Muscle/fat collision and muscle constraint nodes
- When combined with ML Deformer, train on Otis output then run inference in real time

### Gaussian Splatting (Native in H21)

- Karma and Solaris now support Gaussian Splats natively
- Vellum simulation works with Gaussian Splats
- URL: https://entagma.com/new-in-houdini-21-gaussian-splatting-with-vellum/

### Synthetic Data Generation

- Houdini as a platform for generating training data for external ML/AI models
- SideFX partnership with Endava for computer vision synthetic data
- SideFX Labs publishes tools for dataset variation and annotation (SOP, LOP, TOP HDAs)
- No coding required for many workflows
- URL: https://www.sidefx.com/industries/synthetic-data/

---

## 2. AI-Powered Complementary Tools

### Texture Generation

**Adobe Substance 3D (Sampler + Painter)**
- Firefly-powered Text to Texture and Text to Pattern in Sampler
- Image to Texture: any reference image becomes a seamless material via AI
- New Ribbon assets in Painter 12.0 (March 2026)
- Pricing: Substance 3D Collection ~$50/month, or Texturing plan ~$20/month
- URL: https://www.adobe.com/products/substance3d.html

**Polycam AI Texture Generator**
- Free text-to-texture tool generating tileable textures from prompts
- Downloads as standard texture files, compatible with any 3D software including Houdini
- URL: https://poly.cam/tools/ai-texture-generator

**Scenario AI**
- Specializes in game-ready PBR materials
- Generates full map sets (albedo, normal, roughness, metallic) in seconds
- URL: https://www.scenario.com

### 3D Model Generation

**Meshy**
- Text/image to 3D model with AI UV mapping
- Exports OBJ/FBX/GLB for import into Houdini
- Plugins for Blender, Unity, Unreal (no native Houdini plugin, but standard export formats work)
- Pricing: Free (200 credits/month), Pro $10/month, Studio $30/month
- URL: https://www.meshy.ai

**Tripo3D**
- Clean quad-based topology, good for game assets
- Cheapest paid option at $12/month
- Standard format exports for Houdini import
- URL: https://www.tripo3d.ai

**Rodin (by Deemos/Hyper3D)**
- Best for photorealistic objects
- HighPack option: 4K textures, high-poly output
- Pricing: Business from $120/month
- URL: https://hyperhuman.deemos.com

**3D AI Studio**
- Aggregator accessing multiple AI models (Meshy, Rodin, Tripo, others)
- 1,000 credits/month at $14
- URL: https://www.3daistudio.com

**Generative AI inside Houdini (via SideFX Labs)**
- Trellis, Hunyuan, and curated Hugging Face/Civitai models can be used inside Houdini's procedural system
- Prompt-driven mesh generation within your Houdini scene

### Motion Capture & Animation

**DeepMotion**
- AI motion capture from regular video in a web browser
- Exports FBX/BVH for Houdini import
- Clean motion data suitable for direct use on rigs
- URL: https://www.deepmotion.com

**Cascadeur**
- AI-assisted keyframe animation software
- Physics-aware posing and animation cleanup
- Free for non-commercial use, paid plans from ~$12/month
- URL: https://cascadeur.com

**RADiCAL**
- Browser-based video to motion capture, no gear needed
- Exports standard motion data formats
- URL: https://radicalmotion.com

**Move AI**
- Most accurate for complex poses
- Markerless motion capture from multi-camera video
- URL: https://www.move.ai

**Autodesk Flow Studio (formerly Wonder Studio)**
- AI-powered CG character replacement in live-action footage
- Automatic motion tracking, lighting matching, and compositing
- Can export character animation data for use in Houdini
- Pricing: Free tier available, Lite $10/month, Standard $45/month, Pro $95/month
- URL: https://wonderdynamics.com

**Typical pipeline**: Capture in DeepMotion/RADiCAL > polish in Cascadeur > import FBX into Houdini KineFX/APEX

### AI Rendering & Post-Processing

**NVIDIA OptiX Denoiser**
- Built into Houdini Karma (both CPU and XPU)
- AI-trained denoiser reduces render times dramatically
- Requires NVIDIA GPU (Kepler or later)
- Free (included with NVIDIA drivers)
- URL: https://developer.nvidia.com/optix-denoiser

**Intel Open Image Denoise (OIDN)**
- Also built into Karma, works out of the box
- CPU-based, no NVIDIA GPU required
- Free

**Topaz Video AI**
- AI upscaling, frame interpolation, stabilization, denoising
- Can upscale Houdini renders from lower resolution to 4K
- Frame interpolation for smooth slow-motion from simulation renders
- Integrates with DaVinci Resolve, Premiere Pro, After Effects
- Pricing: From $25/month (subscription model since September 2025)
- URL: https://www.topazlabs.com/topaz-video

### AI Video Generation (Complementing Houdini)

These tools complement rather than replace Houdini work:

**Runway Gen-4**
- Best temporal consistency and motion control
- In-video VFX-style editing (paint out objects, change backgrounds, modify lighting)
- Character consistency across shots
- Use case: rapid previsualization, concept exploration, background plates
- URL: https://runwayml.com

**Kling 2.0/2.6**
- 40% cheaper than Runway, equivalent quality
- Generates continuous 2-minute clips
- Simultaneous audio-visual generation
- URL: https://klingai.com

**Pika**
- Quick iteration for motion concepts
- Up to 12-second clips
- URL: https://pika.art

**How these complement Houdini**: Use for rapid concept/mood exploration before committing to full 3D production. Generate reference footage for client pitches. Create background plates. Test camera moves and compositions before building scenes.

### Concept Art & Reference Generation

**Midjourney**
- Industry standard for concept art and lookdev reference
- Use for generating texture references, environment concepts, character designs before 3D execution
- Pricing: Basic $10/month, Standard $30/month, Pro $60/month
- URL: https://midjourney.com

**Stable Diffusion (via ComfyUI)**
- Can be integrated directly into Houdini via the ComfyUI plugin (see Section 6)
- Free/open source, runs locally
- URL: https://stability.ai

### Gaussian Splatting Tools

**GSOPs (Gaussian Splatting Operators for Houdini)**
- Free plugin for full Gaussian Splatting editing in Houdini
- Real-time viewport rendering, import/export, animation, relighting
- Supports 2DGS and 3DGS formats
- Karma and Solaris support
- Compatible with Houdini 20.5 and 21.0 (Windows and macOS)
- URL: https://github.com/cgnomads/GSOPs

**Luma AI**
- Phone-based 3D capture via Gaussian Splatting
- Export as .ply for import into Houdini/GSOPs
- Splats are points in Houdini, easy to manipulate/rig/animate
- Free capture app
- URL: https://lumalabs.ai

---

## 3. AI Coding Assistants for Houdini

### ChatGPT Custom GPTs

**VEX MASTER FOR HOUDINI**
- Custom GPT specialized in VEX scripting for Houdini
- Handles dynamics, simulations, and 3D scene creation code
- Free with ChatGPT Plus ($20/month)
- URL: https://chatgpt.com/g/g-hGR24k8gl-vex-master-for-houdini

**Houdini WizOfVex 1.0**
- Specialized for generating VEX code for Attribute Wrangle nodes
- URL: https://chatgpt.com/g/g-AdHy9U0ZM-houdini-wizofvex-1-0

### Direct ChatGPT/Claude Integration in Houdini

**OpenAI Wrangle / OpenAI Python nodes**
- SideFX tutorial showing how to integrate ChatGPT directly inside Houdini
- "OpenAI Wrangle" node generates VEX code, "OpenAI Python" generates Python code
- Query AI without leaving Houdini
- URL: https://www.sidefx.com/tutorials/how-to-integrate-chatgpt-openai-in-houdini/

### Claude / ChatGPT via Browser

- Both Claude and ChatGPT handle VEX code generation well for common tasks
- Best for: writing Attribute Wrangle snippets, Python SOPs, HDA parameter expressions, PDG processors
- Tips: Always specify Houdini context (SOP, DOP, VOP, CHOP), provide attribute names, describe the geometry structure
- Claude (Opus/Sonnet) tends to produce cleaner VEX with fewer hallucinated function names than earlier GPT models

### AI for Houdini Python Scripting

- Automate repetitive tasks: batch file operations, node graph setup, parameter linking
- Generate hou module scripts for shelf tools and HDAs
- Write PDG/TOP processors in Python
- Both ChatGPT and Claude are strong here since Python is well-represented in training data

---

## 4. Specific Houdini + AI Workflows

### ComfyUI-Houdini Bridge (Rafael Drelich)

- Toolkit that runs diffusion models, AI-driven animation, and batch image processing directly in Houdini
- Bridges Houdini's procedural system with Stable Diffusion and other generative AI
- Workflows spanning motion capture to AI-powered image and video generation
- Available on GitHub with Discord community
- Use cases: AI-assisted texture creation, concept-to-3D pipeline, AI-enhanced compositing
- URL: https://www.sidefx.com/learn/talks/houdini-comfyui-bridge-a-cg-ai-toolkit/

### ML Deformer Production Pipeline

1. Build character rig in APEX
2. Run full Otis tissue/muscle simulation on animation sequences
3. Train ML Deformer on the simulation output
4. Deploy trained model for real-time playback
5. Result: Production-quality deformation at interactive speeds

### Pyro Upres Pipeline

1. Run low-resolution pyro simulation (fast iteration)
2. Apply ML Volume Upres to add high-frequency detail
3. Render the upscaled result
4. Savings: 10-50x faster than running high-res sim from scratch

### Synthetic Data for Client ML Projects

1. Build procedural scene in Houdini (SOPs/LOPs)
2. Use PDG/TOPs to generate thousands of variations
3. Auto-annotate with SideFX Labs synthetic data tools
4. Export labeled datasets for training computer vision models
5. This is a high-value service offering for studios

### AI-Assisted Lookdev Pipeline

1. Generate concept art with Midjourney/Stable Diffusion
2. Use Substance 3D AI to create materials from reference images
3. Import into Houdini Solaris/Karma for scene assembly
4. Use Copernicus ML filters for final image processing

### Gaussian Splatting Capture-to-Animation Pipeline

1. Capture real-world scenes/objects with Luma AI or similar
2. Import .ply into Houdini via GSOPs
3. Edit, clean, composite splat scenes
4. Animate/simulate with Vellum (native H21 support)
5. Render in Karma with Solaris

---

## 5. AI Tools for the Business Side

### Proposal & Pitch Creation

**Bookipi Proposal AI**
- Fast proposal generation integrated with invoicing, contracts, e-signatures
- Free tier available
- URL: https://bookipi.com/proposal-ai/

**Storydoc**
- Web-based, animated proposals with engagement analytics
- Tells you which slides clients spend time on
- URL: https://www.storydoc.com

**Proposal Genie**
- Instant job-specific proposals, Chrome extension for Upwork/Freelancer
- URL: https://www.proposalgenie.ai

**ChatGPT/Claude for Proposals**
- Write scope documents, project timelines, technical breakdowns
- Generate client-facing explanations of complex VFX processes
- Draft SOWs (Statements of Work) and rate cards

### Client Communication

- ChatGPT/Claude for drafting professional emails, status updates, feedback responses
- Summarize complex technical decisions for non-technical clients
- Generate meeting notes and action items from rough notes

### Portfolio Presentation

**ArtStation** - Industry standard for VFX/animation/game art portfolios. Free.
URL: https://www.artstation.com

**Sketchfab** - Interactive 3D model viewer, embeddable. Clients can rotate/zoom models.
URL: https://sketchfab.com

**Webflow** - Custom portfolio websites with full design control.
URL: https://webflow.com

**AI for Showreels**: Use Topaz Video AI to upscale older work, Runway for quick motion graphics intros, ChatGPT/Claude for writing compelling project descriptions.

### Project Management

**Motion** - AI-powered task scheduling, auto-prioritization. $19/month.
URL: https://www.usemotion.com

**Notion AI** - Built-in AI for notes, project tracking, documentation. $10/month add-on.
URL: https://www.notion.so

**Linear** - Fast project management popular with technical teams. Free for small teams.
URL: https://linear.app

---

## 6. Community Resources & Learning

### Courses

**Entagma - Machine Learning 101**
- Create training data in Houdini, build and train neural nets with PyTorch, integrate into Houdini via ONNX
- By Moritz Schwind and Manuel Casasola Merkle
- URL: https://entagma.com/courses/machine-learning-101/

**Houdini School - AI for Houdini Artists (HS-238)**
- Text prompting with ChatGPT API inside Houdini
- Diffusion models (Stable Diffusion) and LLMs in Houdini workflows
- URL: https://www.houdini.school/courses/hs-238-ai-for-houdini-artists

**Entagma - Houdini 21 ML Tools Overview**
- Free walkthrough of all new ML tools in H21
- URL: https://entagma.com/new-in-houdini-21-all-new-machine-learning-tools/

### SideFX Official Resources

**Houdini HIVEai 2025 Recordings**
- Full presentations from the HIVEai event covering ML + proceduralism
- Topics: ComfyUI integration, latent space visualization, ML translation from papers to tools, panel on AI and creativity
- URL: https://www.sidefx.com/community/houdini-hiveai-2025/

**SideFX ML Documentation**
- Complete documentation on ML nodes, training pipelines, ONNX integration
- URL: https://www.sidefx.com/docs/houdini/news/21/ml.html

**SideFX SIGGRAPH 2025 Presentations**
- URL: https://www.sidefx.com/houdini-hive/siggraph-2025/

**SideFX Content Library**
- Pre-built ML examples (ML Deformer, ML Groom Deformer, ML Gauge Synthetic Data)
- URL: https://www.sidefx.com/contentlibrary/

### Community Wiki & Resources

**Houdini CGWiki (Tokeru)**
- Community-maintained wiki with APEX documentation
- URL: https://tokeru.com/cgwiki/HoudiniApex.html

**Procegen ML Tutorials List**
- Curated list of machine learning tutorials for Houdini
- URL: https://procegen.konstantinmagnus.de/machine-learning-tutorials-for-houdini

**Kiryha Houdini Wiki - AI For Artists**
- GitHub-based wiki on AI integration for Houdini artists
- URL: https://github.com/kiryha/Houdini/wiki/AI-For-Artists

### Key Educators

- **Entagma** (Moritz Schwind & Manuel Casasola Merkle): ML courses, Houdini 21 coverage, Gaussian Splatting tutorials
- **Junichiro Horikawa**: Computational/algorithmic design tutorials (Patreon)
- **Rafael Drelich**: ComfyUI-Houdini bridge creator, HIVEai presenter
- **Andreas KJ**: APEX auto-rigging tutorials, Copernicus compositing guides

---

## Quick Reference: Top Picks by Use Case

| Use Case | Tool | Pricing | Impact |
|---|---|---|---|
| Speed up character deformation | Houdini ML Deformer | Included | Real-time playback of CFX-quality results |
| Upscale pyro sims | Houdini ML Volume Upres | Included | 10-50x faster than high-res sim |
| Generate 3D assets fast | Meshy / Tripo3D | $10-12/month | Rapid prototyping and background assets |
| AI motion capture | DeepMotion / RADiCAL | Free tiers available | Skip expensive mocap sessions |
| CG character in live action | Autodesk Flow Studio | Free-$95/month | Rapid VFX compositing |
| AI textures | Substance 3D Sampler | ~$20-50/month | Text/image to PBR materials |
| Free tileable textures | Polycam AI Texture | Free | Quick texture generation |
| Concept/reference art | Midjourney | $10-60/month | Fast lookdev and pitch visuals |
| AI in Houdini viewport | ComfyUI Bridge | Free (open source) | Stable Diffusion inside Houdini |
| Render denoising | OptiX / OIDN in Karma | Free (built in) | Dramatically reduce render times |
| Upscale/interpolate renders | Topaz Video AI | From $25/month | 4K output from lower-res renders |
| VEX code generation | Claude / ChatGPT | $20/month | Faster scripting and problem-solving |
| Gaussian Splatting | GSOPs + Luma AI | Free | Real-world capture in Houdini |
| Client proposals | Bookipi / Storydoc | Free tiers | Professional proposals in minutes |
| Project management | Motion / Notion AI | $10-19/month | AI-powered scheduling |

---

## Key Takeaway

The highest-impact AI tools for a Houdini specialist fall into three tiers:

**Tier 1 - Use immediately (built into Houdini 21)**:
ML Deformer, ML Volume Upres, Neural Point Surface, OptiX/OIDN denoising, Copernicus ML filters, ONNX runtime

**Tier 2 - High ROI complementary tools**:
Claude/ChatGPT for VEX/Python scripting, Midjourney for concept art, Substance 3D AI for textures, DeepMotion/RADiCAL for mocap, GSOPs for Gaussian Splatting, ComfyUI-Houdini bridge

**Tier 3 - Business multipliers**:
AI proposal tools, Topaz Video AI for portfolio upscaling, Flow Studio for quick VFX comps, AI video generators for concept pitches
