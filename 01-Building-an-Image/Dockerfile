# use alpine node image as a base image
FROM node:alpine

# set working directory
WORKDIR /app

# copy package before the rest to run unchached "npm install" only when the
#package is changed
COPY package.json .

# run "npm i" command in the intermediate container, the resulting container environment will be copied to the image
RUN npm install

# copy everything from root directory to the working directory of the image
COPY . .

# store "npm run start" in the image and launch it when container is being started
CMD ["npm", "run", "start"]


# RUN is an image build step, the state of the container after a RUN command will be
# committed to the container image. A Dockerfile can have many RUN steps that layer on
# top of one another to build the image. CMD is the command the container executes by
# default when you launch the built image.
