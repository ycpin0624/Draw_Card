<template>
  <div id="Flush">
    <input
      id="FlushButton"
      type="button"
      class="add"
      value="洗牌"
      onclick="location.reload()"
    />
  </div>
</template>

<style>
#FlushButton {
  width:100px;
  position: absolute;
  font-size: 20px;
  cursor: pointer;
  color: #ffffff;
  text-align: center;
  background-color: #ad0000;
  border-radius: 3px;
  border-style: none;
  top: 75%;
  left: 47%;
}
#FlushButton:hover {
  animation: scaleDrawIN 0.3s ease;
  transform: scale(1.05);
}

#FlushButton:not(:hover) {
  animation: scaleDrawOUT 0.3s ease;
}
@keyframes scaleDrawIN {
  0% {
    transform: scale(1);
  }
  100% {
    transform: scale(1.05);
  }
}

@keyframes scaleDrawOUT {
  0% {
    transform: scale(1.05);
  }
  100% {
    transform: scale(1);
  }
}
</style>