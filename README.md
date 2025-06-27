This is a text to video generator.
It uses stable diffusion to generate images from the prompt and and then uses those generated images to make a video.
It uses moviepy library to compile images to a video and also add audio to it. Audio should be provided , it is not generated.
You have to only provide a initial prompt, it will then give that prompt to llm api(zephyr-7b-beta) which will make a script and and then generate prompts for images for that script and those prompts are then given to Stable diffusion model to generate bulk of images
Then those images generated are compiled using moviepy with audio provided.


Problems still left:
*Every time answer to prompt given by llm is in different style making it difficult to extract only prompts which are to be given to Diffusion model.
Solution to try : 1) give the answer of prompt as a prompt again to llm and take its help in extracting only the prompts 
                  2) change the current prompt to have the llm give the prompts cased in some special characters and then use string manipulation to extract only the prompts as trying to get it to give only prompts without additional text has failed no matter how many times i tried.
*The audio for video is to be provided(depends on requirements)
solutions to try:1) depending on application we need we can also generate script from llm for the video and then use a text to speech model
                  2) generate our on audio using some audio generating model
* the images are not consistent: so generating an effective video from them is not possible
  solution:somehow add character consistency to image generation

# i have provided a video i made using this technique.it is a simple video.
note : when this video was made i provided the hard coded prompts for image generation and llm api was not integrated yet .. i couldn't make one after api integration because i was working on colab and its gpu access is revoked for the time being and without gpu it takes more than 40 mins for single image generation.
