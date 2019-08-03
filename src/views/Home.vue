<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/storyTime.jpg">
        <p>Ai is trained on quotes from <a href="https://stocism.netlify.com/">my stocism site</a></p>

    <input type="text" v-model="inputText"><button @click="train(inputText)">Train</button>
    {{output}}
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
  import brain from 'brain.js'

export default {
  name: 'home',
  data(){
    return{
      inputText:'',
      output:''
    }
  },
  components: {
    // HelloWorld
  },
  methods:{
    train(inputText){
     const trainingData = [
          "Waste no more time debating what a good man should be, just be one.", "At daybreak, when you are reluctant to rise from b…should nuzzle under the bedclothes and keep warm?", "Men seek out retreats for themselves in the countr…eful or more free from trouble than his own soul.", "Be like a headland of rock against which the waves…s and around it the crashing waters come to rest.", "In but a short while you shall be ashes, or a few …es, and possibly just a name, or not even a name.", "Watch the stars in their courses as one who runs a… these cleanse away the dross of earthbound life.", "Look within yourself. Within is the fountain of go…eady to gush forth if you will always dig for it.", "The mind, unconquered by violent passions, is a ci… in which to find refuge and remain safe forever.", "The cucumber is bitter. Throw it away. There are b… to add “Why are such things found in the world?”", "Take a bird’s-eye view of the world: it's endless …things coming to be, existing, and ceasing to be.", "All you need are these: certainty of judgment in t… present moment for anything that comes your way.", "From Rusticus... I learned to read carefully and n…with those who have a lot to say about something.", "Frame your thoughts like this—you are an old perso…bout your present fortune or dreading the future.", "Whenever someone has done wrong by you, immediatel…you’ll be more readily gracious for their error.”", "Your mind will take the shape of what you frequent…r the human spirit is colored by such impressions", "Pay close attention in conversation to what is bei…n words, listen closely to what’s being signaled.", "If anyone can prove and show to me that I think an…ed is the one who abides in deceit and ignorance.", "Don’t set your mind on things you don’t possess as… point of being troubled if you should lose them.", "I’m constantly amazed by how easily we love oursel… peers have of us and how little to our very own!", "What is your vocation? To be a good person.", "How beautifully Plato put it. Whenever you want to… together and arranged in a pairing of opposites.", "Don’t be ashamed of needing help. You have a duty …nd can’t climb up without another soldier’s help?", "In your actions, don’t procrastinate. In your conv…ssive. In your life, don’t be all about business.", "Receive without pride, let go without attachment", "Often injustice lies in what you aren’t doing, not only in what you are doing.", "It is essential for you to remember that the atten…with lesser things beyond what should be allowed.", "What if someone despises me? Let them see to it. B…show off my patience, but genuinely and usefully.", "Remember that to change your mind and to follow so…se and judgment, and yes, with your intelligence.", "The person who does wrong, does wrong to themselve…n is unjust to themselves—making themselves evil.", "The best way to avenge yourself is to not be like that.", "There’s nothing worse than a wolf befriending shee…t should show in your eyes and not escape notice.", "There is no evil in things changing, just as there is no good in persisting in a new state.", "When you are distressed by an external thing, it’s…. And you can wipe this out at a moment’s notice.", "If someone is slipping up, kindly correct them and…ssed. But if you can’t, blame yourself—or no one.", "Let each thing you would do, say or intend be like that of a dying person.", "Think of the whole universe of matter and how smal…workings of fate and how infinitesimal your role.", "It’s a disgrace in this life when the soul surrenders first while the body refuses to.", "Everything has two handles. One by which it can be carried and another by which it cannot.", "Some things are up to us and other are not… Rememb…e distressed, and will blame both gods and men...", "Never to say of anything 'I have lost it' but that you have given it back.", "Don’t seek for everything to happen as you wish it…s it actually will—then your life will flow well.", "People are not disturbed by events, but by their judgements about events. ", "If the room is smoky, but only moderately, I will …keep a firm grasp of it, the door is always open.", "For it is neither death nor pain that is to be feared but rather the fear of pain or death.", "A person untrained in philosophy blames others whe…eady complete blames neither another nor himself.", "Disease is a hindrance to the body but not to the …hindrance to something else, but not to yourself.", "With regard to everything that befalls you, rememb…lf and see what faculty you have to deal with it.", "If someone handed your body over to anyone you met…essed and troubled – are you not ashamed of that?", "When you are about to meet someone, particularly w… at a loss regarding how to act on that occasion.", "Make it your practice to say to every harsh impres…r, be prepared to respond, ‘It is nothing to me.‘", "The chief task in life is simply this: to identify… but within myself to the choices that are my own", "What is the fruit of these teachings? Only the mos…f wisdom who say that only the educated are free.", "Some things are in our control, while others are n…k, slavish, can be hindered, and are not our own.", "The proper work of the mind is the exercise of cho…nctioning? Nothing but its own corrupt decisions.", "If you wish to improve, be content to appear cluel… some regard you as important, distrust yourself.", "When I see an anxious person, I ask myself, what d…n control, why would they be stricken by anxiety?", "Who then is invincible? The one who cannot be upset by anything outside their reasoned choice.", "Of all the things that are, some are good, others … wealth, health, life, death, pleasure, and pain.", "In public avoid talking often and excessively abou…o pleasant for others to hear about your affairs.", "It isn’t events themselves that disturb people, but only their judgments about them.", "There are two things that must be rooted out in hu…orrent of circumstance there can be no happiness.", "Those who receive the bare theories immediately wa…e craft of artisans show in what they’ve learned.", "That’s why the philosophers warn us not to be sati…and hold opinions the opposite of what we should.", "You can bind up my leg, but not even Zeus has the power to break my freedom of choice.", "Consider who you are. Above all, a human being, ca… other things, and is free from any other master.", "Don’t trust in your reputation, money, or position…d lifts us eye to eye with the rich and powerful.", "In short, you must remember this—that if you hold …you will have destroyed your capacity for choice.", "Everywhere means nowhere. When a person spends all…nds by having many acquaintances, but no friends.", "You can tell the character of every man when you see how he gives and receives praise.", "Our plans miscarry because they have no aim. When …bour he is making for, no wind is the right wind.", "As long as you live, keep learning how to live.", "Two elements must therefore be rooted out once for… concerns me, and the former concerns me not yet.", "It does not matter what you bear, but how you bear it.", "By looking forward to the coming of our sorrows we take the sting out of them when they come.", "I have applied myself to the society of wise men… … looking out for her assault, easily sustains it.", "The wise man, therefore, being tranquil, and deali…, greedy, and excited by the frenzy of ambition.", "Do you ask what I seek from virtue? I answer, Hers…or she has nothing better; she is her own reward.", "We must give up many things to which we are addict… as petty what the mob regards as most desirable.", "I will keep constant watch over myself and—most us…t our plans for the future descend from the past.", "Let’s pass over to the really rich—how often the o… how few of their possessions they get to keep...", "Many are harmed by fear itself, and many may have come to their fate while dreading fate.", "Nothing will ever befall me that I will receive wi…u should never hope for exemption or seek escape.", "Show me that the good life doesn’t consist in its …who has had a long life to have lived too little.", "We like to say that we don’t get to choose our par… can truly choose whose children we’d like to be.", "We should take wandering outdoor walks, so that th…and refreshed by the open air and deep breathing.", "Many times an old man has no other evidence besides his age to prove he has lived a long time.", "Silence is a lesson learned from the many sufferings of life.", "It’s ruinous for the soul to be anxious about the …it will lose the ability to enjoy present things.", "Therefore, explain why a wise person shouldn’t get…ey go beyond proper measure, are but punishments.", "No person has the power to have everything they wa… to cheerfully put to good use what they do have.", "“Let us prepare our minds as if we’d come to the v…es on their life each day is never short of time.", "The rational soul is stronger than any kind of for…is itself the cause of a happy or miserable life.", "It’s better to conquer grief than to deceive it.", "Leisure without study is death—a tomb for the living person", "From good people you’ll learn good, but if you min…with the bad you’ll destroy such soul as you had.", "For philosophy doesn’t consist in outward display,…g heed to what is needed and being mindful of it.", "How much better is it to be known for doing well b…ng on sticks and stones is it to spend on people.", "As for me, I would choose being sick over living i…eeds injustice because it also breeds greediness."];

const lstm = new brain.recurrent.LSTM();
const result = lstm.train(trainingData, {
  iterations: 1500,
  log: details => console.log(details),
  errorThresh: 0.011
});
console.log(inputText)
const run1 = lstm.run(inputText);
this.output=inputText+' '+run1
          }
  },
  
  
}
</script>
<style lang="scss" scoped>
.home{
  display: flex;
  flex-direction: column;
  img{
    max-width: 1040px;
    margin: 0 auto;
  }
}
</style>
