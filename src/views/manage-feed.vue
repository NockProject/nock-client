<template>
  <div>
    <menuRight />
    <div class="listPost">
      <div class="post">
        <div class="userPost">
          <img src="../assets/img/profilUser.svg" alt="Photo de profil" />
          <div class="infoProfil">
            <p>Nom Prénom</p>
            <p>Il y a 1h</p>
          </div>
          <h3>Exemple d'un titre pour un post</h3>
        </div>
        <div class="delete">
          <img src="../assets/icons/delete.svg" alt="icon delete" />
        </div>
      </div>
      <div class="post">
        <div class="userPost">
          <img src="../assets/img/profilUser.svg" alt="Photo de profil" />
          <div class="infoProfil">
            <p>Nom Prénom</p>
            <p>Il y a 1h</p>
          </div>
          <h3>Exemple d'un titre pour un post</h3>
        </div>
        <div class="delete">
          <img src="../assets/icons/delete.svg" alt="icon delete" />
        </div>
      </div>
      <div class="post">
        <div class="userPost">
          <img src="../assets/img/profilUser.svg" alt="Photo de profil" />
          <div class="infoProfil">
            <p>Nom Prénom</p>
            <p>Il y a 1h</p>
          </div>
          <h3>Exemple d'un titre pour un post</h3>
        </div>
        <div class="delete">
          <img src="../assets/icons/delete.svg" alt="icon delete" />
        </div>
      </div>
      <div class="post">
        <div class="userPost">
          <img src="../assets/img/profilUser.svg" alt="Photo de profil" />
          <div class="infoProfil">
            <p>Nom Prénom</p>
            <p>Il y a 1h</p>
          </div>
          <h3>Exemple d'un titre pour un post</h3>
        </div>
        <div class="delete">
          <img src="../assets/icons/delete.svg" alt="icon delete" />
        </div>
      </div>
      <div class="post">
        <div class="userPost">
          <img src="../assets/img/profilUser.svg" alt="Photo de profil" />
          <div class="infoProfil">
            <p>Nom Prénom</p>
            <p>Il y a 1h</p>
          </div>
          <h3>Exemple d'un titre pour un post</h3>
        </div>
        <div class="delete">
          <img src="../assets/icons/delete.svg" alt="icon delete" />
        </div>
      </div>
      <div class="post">
        <div class="userPost">
          <img src="../assets/img/profilUser.svg" alt="Photo de profil" />
          <div class="infoProfil">
            <p>Nom Prénom</p>
            <p>Il y a 1h</p>
          </div>
          <h3>Exemple d'un titre pour un post</h3>
        </div>
        <div class="delete">
          <img src="../assets/icons/delete.svg" alt="icon delete" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import menuRight from "../components/menu-right";

export default {
  components: {
    menuRight
  }
};
</script>

<style lang="scss" scoped>
.listPost {
  margin-top: 50px;

  .post {
    background-color: #ffffff;
    margin: 10px;

    -webkit-box-shadow: 0 3px 6px -2px rgba(0, 0, 0, 0.5);
    -moz-box-shadow: 0 3px 6px -2px rgba(0, 0, 0, 0.5);
    box-shadow: 0 3px 6px -2px rgba(0, 0, 0, 0.5);

    .userPost {
      display: inline-block;
      vertical-align: top;
      box-sizing: border-box;
      width: 70%;
      border-radius: 5px;
      margin: 10px;

      h3 {
        margin: 10px 0 0 60px;
        font-size: 14px;
      }

      img {
        display: inline-block;
        vertical-align: top;
        box-sizing: border-box;
        width: 40px;
        height: 40px;
      }

      .infoProfil {
        display: inline-block;
        vertical-align: top;
        box-sizing: border-box;
        width: 70%;

        p:first-child {
          margin: 0 0 0 20px;
          font-size: 12px;
          font-weight: 600;
        }

        p:last-child {
          margin-left: 20px;
          font-size: 10px;
          font-weight: 400;
        }
      }
    }

    .delete {
      display: inline-block;
      vertical-align: top;
      box-sizing: border-box;
      width: calc(100% - (70% + 20px));
      text-align: right;
      padding: 10px 10px 0 0;
    }
  }
}
</style>
