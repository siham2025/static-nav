<template>
	  <div class="wrapper">
          <h1>Our Team</h1>
          <div class="team">
            <div class="team_member" v-for="(team, i) in teams" :key="i">
              <div class="team_img">
                <img :src="getCorrectImg(team.profilePic)" alt="Team_image">
              </div>
              <h3>{{ team.firstName }}</h3>
              <p class="role">{{ team.jobTitle }}></p>
              <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Est quaerat tempora, voluptatum quas facere dolorum aut cumque nihil nulla harum nemo distinctio quam blanditiis dignissimos.</p>
            </div>
          </div>
        </div>
</template>

<script setup>
import { teams } from '@/data/appTeams.js'
// TODO: boucler sur le tableau d'objet 

console.log(teams)

const getCorrectImg = (profilePic) => {
  profilePic = profilePic.replace('.jpg', '_round.png').replace('profil', 'profile')
  return `/img/${profilePic}`
}
</script>


<style scoped>
@import url('https://fonts.googleapis.com/css?family=Allura|Josefin+Sans');

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}


.wrapper{
    width:100%;
    height:100%;
    border-radius:20px;
    background: #e5d2b5;
    font-family: 'Josefin Sans', sans-serif;
    margin-top: 50px;
}

.wrapper h1{
  font-family: 'Allura', cursive;
  font-size: 52px;
  margin-bottom: 60px;
  text-align: center;
}

.team{
  display: flex;
  justify-content: center;
  width: auto;
  text-align: center;
  flex-wrap: wrap;
}

.team .team_member{
  background: #fff;
  margin: 5px;
  margin-bottom: 50px;
  width: 300px;
  padding: 20px;
  line-height: 20px;
  color: #8e8b8b;
  position: relative;
}

.team .team_member h3{
  color: #81c644;
  font-size: 26px;
  margin-top: 50px;
}

.team .team_member p.role{
  color: #ccc;
  margin: 12px 0;
  font-size: 12px;
  text-transform: uppercase;
}

.team .team_member .team_img{
  position: absolute;
  top: -50px;
  left: 50%;
  transform: translateX(-50%);
  width: 100px;
  height: 100px;
  border-radius: 50%;
  background: #fff;
}

.team .team_member .team_img img{
  width: 100px;
  height: 100px;
  padding: 5px;
}

</style>