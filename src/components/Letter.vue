<template>
  <div class="letter-box">
    <div class="box">
      <div class="note">
        <p>
          I know sometimes I'm annoying... But I love you so much. You're man just need time to
          adjust.....
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LetterBox',
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Kite+One&display=swap');

.letter-box {
  display: flex;
  justify-content: center;
  align-items: center;
  height: auto;
  width: auto;
  background: rgba(255, 240, 245, 0.8);
}

.box {
  width: 80%;
  height: 200px;
  border: 2px solid #af4c75;
  border-radius: 15px;
  box-shadow: 0 6px 12px rgba(255, 100, 180, 0.6);
}

.note {
  font-size: 16px;
  color: #ff66b2;
  text-align: center;
  padding: 4rem 1rem 0rem;
  z-index: 2;
  font-family: 'Kite One', sans-serif;
  font-weight: bold;
  position: relative;
}
</style>
