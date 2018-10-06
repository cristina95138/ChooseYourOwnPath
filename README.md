# ChooseYourOwnPath

var energyLevel = 100;
buttonminusClick("sleepButton","sleepScreen","sleepEnergy");
buttonminusClick("upButton","upScreen","upEnergy");
buttonminusClick("surveyButton","surveyingScreen","surveyingEnergy");
buttonminusClick("thinkButton","thinkingScreen","thinkingEnergy");
buttonminusClick("insteadsurveyButton","surveyingScreen","surveyingEnergy");
buttonminusClick("readButton","clueScreen","clueEnergy");
buttonminusClick("ignoreButton","lostScreen","lostEnergy");
buttonplayagainClick("playagainButton","sleepEnergy");
buttonminusClick("rememberingButton","rememberingScreen","rememberingEnergy");
buttonminusClick("followrememberingButton","lostScreen","lostEnergy");
buttonminusClick("surveyinsteadButton","surveyingScreen","surveyingEnergy");
buttonminusClick("wButton","wonScreen","wonEnergy");
buttonminusClick("eButton","lostScreen","lostEnergy");
buttonminusClick("nButton","lostScreen","lostEnergy");
buttonminusClick("sButton","lostScreen","lostEnergy");
buttonplayagainClick("playagainButton2","sleepEnergy");
buttonplayagainClick("playagainButton3","sleepEnergy");
function buttonminusClick(id,screen,energyid) {
  onEvent(id, "click", function() {
    reduceenergyLevel();
    energyLevel = energyLevel-5;
    setScreen(screen);
    setText(energyid, energyLevel);
    energylevelZero();
});
}
function reduceenergyLevel() {
  energyLevel = energyLevel-5;
}
function energylevelZero() {
  if (energyLevel===0) {
  setScreen("ranoutScreen");
 }
}
function buttonplayagainClick(id,energyid) {
  onEvent(id, "click", function() {
    setScreen("sleepScreen");
    energyLevel = 100;
    setText(energyid, energyLevel);
  });
}
