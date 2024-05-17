# Group-report-5
Introduction (Su) 

The primary goal of our project is to investigate language characteristics by using skin care product reviews as our data source. When individuals are considering the purchase of a product, they often reference the associated customer reviews. These language features extracted from the reviews can heighten a person's interest in and desire to acquire the product.
By observing the sentiment expressed within these product reviews, we aim to analyze how the reviews influence customer purchasing decisions. Do positive reviews lead to a higher likelihood of the customer making a purchase? Conversely, do negative reviews deter potential customers? Through this analysis, we hope to develop a model that can predict the chances of a customer re-purchasing a product based on the language used in the existing reviews.
Ultimately, a deeper understanding of how product review language impacts consumer behavior could provide valuable insights for companies seeking to optimize their marketing strategies and improve customer satisfaction. The findings from this project may enable businesses to better cater to the needs and preferences of their target audience.


Methodology

Our research targets mainly focus on 3 fields, product reviews from editors, shopping platforms, and official websites. After obtaining around 60 reviews from various skin care review websites, the following steps are data cleaning and annotation of the data we collected. For the data cleaning part, we will use Python, input the code, cleaning unnecessary information from the reviews from colab, for example, punctuation and spacing. We believe that punctuation can’t tell the difference or represent individual emotions. Thus, we need a pure text to focuse on the literal meaning or wording of the respondents. For adding annotation, we believe that even data cleaning the unnecessary items, not the whole texts could show buyer consumption choices or emotions. Hence, we created equivalent annotations and then marked in the text, the progress would better assist us to extract useful information or elements which benefical to our further analysis. 



Data 
Segmentation Annotation

1. <PD>= Product >Product name  
Define: Products highlighted in reviews 
Eg: <PD>Peach & Lily</PD>,<PD>toner</PD> 

2. <+> Positive  >Score + proportion
<-> Negative  >Score + proportion
Five points is the highest, and the number will be rounded to an integer.Then based on the content of the comments, the proportion  of positive and negative sentence by comments

Eg: Score: 4/5 
 <G>Spread smoothly around the eye area.</G>, <B>The hydrating effect doesn't last long</B>

3. <T> = Time (Daily routine) 

Define: Daily habits shared by users
Eg: <T>After sleep</T> , <T>in the morning and night</T>
<G>= GOOD REVIEWS >Word choice
<B>=BAD REVIEWS   >Word choice

4. Paid = accepting money
   Genuine = does not represent any position 


Id:1  (2)  Combination / Lips Product / Genuine
<->not great</->
<+>it looked cute and smelt pleasant</+> 
<+>like</+>
<T>some time now</T> 
<B>not at all satisfied with this product it is not at par with the standards of sephora color is patchy moisturizing strength is not too good it barely <T>stays for 23 hrs</T>。 and feels like a greasy goo on the lips</B> 
<->wouldnt</-> 

Id:2 (5) NA /Lips Product/Genuine
<PD>vaseline lip therapy petroleum jelly</PD>                             
<+>amazing</+>
<T>every night</T>
<G>this product stopped my lips from cracking and got rid of the dry skin at the edge of my lips and stopped it from peeling i drink water to damp my lips and then use the product to lock the moisture in and my lips feel <+>amazing</+> the <T>next day</T> and also have a natural pinkish glow matters</G> <+>cheap</+>
<+>works so well</+>
<T>at night</T>
 <->inconvenient</->
<T>during the day</T>
<+>like</+>
<PD>cocoa<PD>
 <+>butter</+> 

ID:3 (3) Combination / Lips Product / Genuine
<->expensive</->
<+>alright git</+>
<PD>standard clear stick lip balm</PD> 
<G>with no distinct scentg</G> 
<+>cheaper</+>
 <B>my lips were back to their usual dry chapped look by midday too expensive</B> 
<->not effective enough</->

ID:4 (2)     Normal /Eye Product / Genuine
<->no difference</->
 <T>after 2 months</T> 
<+>pros</+> 
<G>very hydrating at the time of application spread smoothly around the eye area</G>
<->cons</->
<B>the hydrating effect doesnt last long </B>
<->no difference</->
 <T>after using for 2 months</T>
 <B>no improvement simply does nothing other than providing a short moisturizing effect right after application</B> 
<B>jar packaging is not hygienic and product is exposed to light and air that reduce its effectiveness</B> 
<->expensive</->
ID:5 (5) NA/Eye Product/ Genuine
<PD>sephora</PD> 
<PD>a lash serumwas</PD>
 <+>recommended</+>
<->expensive</->
 <T>after 2 months</T>
<+>thicker and longer</+> 
<G>its really lightand absorbs quicklyand im prone to milia cos my eyelids are oily</G> 
<+>surprised and happy</+>
 <+>naturally longer and fluffier</+>
 <+>worth it</+>

ID:6 (4) Combination/Eye Product/ Genuine
<B>not user friendly band pricy </B>
<+>love</+> 
<PD>dr gl products<PD>
 <B>it is quite pricey</B> 
<G>this does brighten my dark eye circles</G> 
<B>the price bottle is not user friendly</B> 
<B>the bottom the suction dropper doesnt work well ended</B> 
<PD>dr gl</PD>

ID:7(2) Dry/Skin Product/Genuine
<PD>pixi peel and polish</PD>
 <PD>the pixo holiday pack</PD>
<PD>peel polish 15 ml tube </PD>
 <PD>mini pixi glow tonic and mud mask</PD>
<+>high hopes</+>
<+>glowy</+> 
<B>it didnt feel any of those and to me it felt like a normal wash off product which gives u very temporary results i didnt see much change in my skin pores nor any improvement in its overall appearance</B> <->didnt like</->

ID:8 (4) Combination/Skin Product/Genuine
<->dry</->
 <->dry</->
 <G>i immediately feel like i have much softer suppler skin which indeed</G>
<+>great feeling</+>
 <->sensitive</->
 <G>have not had any issues with this causing any irritation</G>
 <+>a holy grail</+>

 ID:9 (5)Combination/Skin Product/Genuine
<PD>vaseline pro derma moisturizing with hyaluronic acid body lotion</PD> 
<+>recommend</+> 
<PD>the vaseline body lotion</PD>
 <G>for those with normal to dry skin and also sensitive skin</G>
<+>effective</+> 
<G>leaves my skin feeling deeply moisturised and nourished throughout the entire day the formula also is lightweight and does not feel heavy or sticky at all even in singapores humid weather</G> 
<+>like</+>
<T>everyday</T> 
<+>smoother</+>
<+>moisturised</+>

ID:10 (5)Combination/Sunscreen Product/Genuine
<T>often</T>
<+>best</+>
<PD>innisfree</PD> 
<G>this one controls sebum the most</G>

ID:11(5)Combination/Sunscreen Product/Genuine
<+>good</+> 
<PD>a physical sunscreen</PD>
<+>not break me out</+> 
<G>it also makes my skin look matte and good</G>
 
ID:12 (4)Combination/Skin Product/Genuine
<PD>the body shops vitamin e eye cream</PD> 
<G>hydrates and rejuvenates the delicate eye area with its lightweight formula infused with nourishing vitamin e and wheatgerm oil it absorbs quickly diminishing dark circles and fine lines <T>over time</T></G
 <PD>the body shops</PD> 

ID:13(5) Normal/Lips Product/Genuine
<+>essential</+> 
<PD>lip care</PD> 
<PD>lip balm</PD> 
<+>essential</+>
<G>its straightforward yet potent formula offered fundamental hydration guarding my lips against the brisk arid air of the season portable and effortlessly accessible</G>
 <G>my lips stayed supple and at ease throughout</G>
 <+>a dependable choice</+>

ID:14 (2) Oily/Lips Product/Genuine
<->bad</->
 <PD>the tinted</PD>
<T>since 2017</T>
<+>not bad</+> 
<G>the shades gave a <+>nice</+> tinge to my otherwise colourless lips and it was just an easy cheap fuss free lipbalm</G>
<B>not very moisturising</B> 
<B>it does absolutely nothing at all in terms of moisturising your lips just leaves a waxy layer of colour on top of the lips also it feels really uncomfortable</B>
 <+>affordable price</+>
<+>perfect</+>
 <->avoid</-> 

ID:15 (3) Combination/Skin Product//Genuine
<G>watery scent abit strong</G>
<G>absorbed easily and leaves the right amount of moisture on the surface</G>
<B>i get this weird scent the scent is a bit strong and tends to last for a while on the skin</B>
<->sensitive</->
<G> its high spf</G>
 <+>interesting</+>
 <G>if you want a moisturizer that lightens and brightens skin effectively</G>

ID:16 (4) Combination/Skin Product/Genuine
<PD>nivea creme</PD>
<PD>la mers moisturizers</PD>
<->cannot</->
<+>surprised</+>
 <+>decent</+>
 <->sensitive</-> 
<B>its not the best cream for singapores weather</B>
<G>i think it is a good cream for undereyes or for colder weather especially when you want to lock in the moisture only downside is that it contains fragrance which is not suitable for every skin type</G>

ID:17(5) Dry/Sunscreen Product/Genuine
<PD>athlizm</PD>
<PD>biore athlizm extreme waterproof sunscreen</PD>
<+>right</+> 
<G>it is not too low to be deemed ineffective in our sunny climate despite it being waterproof it spreads well is quickly absorbed into the skin without leaving an uncomfortable residue<G> 
<G>washes off well in the shower</G> 
<T>a long time</T>
 <+>vouch</+>
 <+>efficacy</+> 
<G>i do not have sun spots on my skin to date</G>

ID:18 (3) Combination/Sunscreen Product/Genuine
<->nothing special</->
<->oily</->
 <G>i <+>love</+> the handy design of the product</G>
 <B>it failed to provide me with a matte fresh outlook after application</B>
<->oily</->
 <->not be recommending</->

ID:19 (4) Combination/Skin Product/Genuine
<+>great</+> 
<PD>makeup cleanser</PD>
<+>the best</+> 
<PD>make up cleanser</PD> 
 <+>love</+> 
<G> how easily the cream spreads out on your skin and just melts all your makeup away the cream is rich and creamy hence you wont be tugging on your skin excessively to wipe away the make up</G>
 <B>my only complaint is that the packaging comes in a big twist bottle so you gotta use your clean hands to scoop out</B>
<->not very convenient</->
<->dirty</-> 

ID:20 (1)Dry/Skin Product/Genuine
<->oily</-> 
<B>hard to wash off</B>
<B>consistency between <PD>a cream and a balm</PD> doesnt feel very effective and cant be used for eye makeup as it stings hard to wash off</B>
<B>non friendly packaging</B> 

ID:21 (5) Combination/Eye Product/Genuine
<PD>eyecream</PD>
<G>gets absorbed into the skin really quickly</G> 
<T>during the day</T>
 <+>moisturising</+>
<T>at night</T>
 <G>this product has helped to maintain the elasticity of the skin</G>
<G>at 27 yo mother most people still think that i am 16</G> 
<+>love</+>
 <->unhygienic</->

ID:22 (5) Combination/Lips Product/Genuine
<PD>vaseline lip therapy petroleum jelly rosy lips pink a nourishing lip balm</PD>
<PD>the vaseline lip therapy petroleum jelly rosy lips pink</PD>
<+>exceeded my expectations</+> 
<PD>a nourishing lip balm</PD> 
<G>the packaging</G>
<PD>lip balm</PD>
<G>the small portable container is perfect for onthego use and easily fits into pockets or bags it also has a secure lid ensuring that the product stays intact and doesnt create any mess when it comes to the performance of the lip balm </G>
<+>surprised</+> 
<PD>the vaseline liptherapy petroleum jelly </PD>
 <G>provided intense hydration and moisture to my lips</G>
 <+>soft and supple</+> 
<G>it effectively repaired any dryness or chapping</G>
<+>a healthy and refreshed</+> 
<G>its not too overpowering or bold </G>
 <T>everyday</T> 
<+>smooth and nonsticky</+>
<G>it comfortable to apply it glides effortlessly on the lips</G> 
<G>it didnt feel heavy or greasy</G>




ID: 23 (5) Normal/Cleaning Product/Paid 
<PD> balm <PD>
<G> helps remove makeup excess sebum and impurities without leaving your skin dry a spatula is provided so that you never have to dip your fingers into the product <G> 
<G>  i found that this balm was so effective that my skin was spotless when i came to my second cleansee <G> 
<G>contains some of the best oils  making it perfect  for instant makeup and impurity removal <G> 
<+> incredible </+> 
<+> outstanding reviews </+> 
<+> excellent job </+>
 <+>best </+> 
 <+>perfect</+> 


ID: 24 (4) Normal/Cleaning Product/Paid 
<PD>exfoliator<PD> 
<G> a product doesnt use ingredients to make the product smell sweetwhich i think is a good thing<G>
<+>gentle</+> 
<+>super hydrated <+>
<T>my evening routine twice a week <T>


ID: 25 (5) Normal/skin Care/Paid 
<PD>toner<PD>
<G>help keep skin looking polished <G>
<G>however i found that my skin didnt ever feel dried out <G>
<T> three times per week<T>
<+>good</+> 
<+>fascinating to use </+> 

ID: 26 (5) Normal/skin Care/Paid 
<PD> serum<PD> <PD>nightone<PD> 
<G>achieve the look of glass skin and this serum definitely helped me meet it every time<G> 
<T>onetothree pumps of this serum in the morning <T> 
<+>lightweight</+> 
<+>gave an overall radiance to my complexion</+>


ID: 27 (4) Normal/Cleaning Product/Paid 
<PD>cleansing balm and oilbased cleanser <PD>
<G>i have used it my face always feels incredibly purified from inside to out<G> 
<+>incredibly purified</+>
<+>hypoallergenic </+>
<+>nice</+> 

ID: 28 (3) Sensitive/Cleaning Product/Genuine
<PD>cleanser <PD>
<G>this cleanser would also dry out my skin <G>






ID:32 (5) Combination/ Facial Product/ Genuine
<PD>loreal</PD> 
<B> its not enough for my aging dry skin in winter</B>
 <G><+> great</+>  </G> 
 <PD>loreal creams  </PD> 
<+>good <+/> 
<G> have used most of the jar and it is possible my wrinkles are less obvious it works well as a makeup base</G>

ID:33  (5) Combination/ Lip Product/ Genuine

<T> before bed</T> 
<+> moisturized </+>, This lip balm is a definite keeper for me 
 <+> efficacy </+>
<+> affordability</+> 

ID: 34  (4) Combination/ Facial Product/ Genuine

 <G> when i woke up the next morning to check there was no brown spots</G>
  <+> repaired </+>  
<T> morning  </T>
 <G><+>  happy </+>  
 <PD> estee lauder  advance night repair serum </PD>

ID: 35  (4) Combination/ Facial Product/ Genuine
<PD> lancome </PD>
<T>8 days</T> 
 <G><+>  gentle /+>  
 <G>i don't feel sticky either itch </G>
<+> less oily </+>  
<G> makeup  last longer </G>
<G>it boots up my skin by hydrate yet not oily </G>
<G>it did helps to clear my pimple scar as well as my dark winkle well recommended</G>


ID: 36 (4)Combination/ Facial Product/ Genuine

hands down one of the <G><+> best </+>  make up cleanser</G>
<G> i love how easily the cream spreads out on your skin and just melts all your makeup away </G> 
<+> rich  </+> 
 <+>  creamy </+>  
<B> my only complaint is that the packaging comes in a big twist bottle so you gotta use your clean hands to scoop out however much of the product you need at one go not very convenient </B> 


ID: 37  (4) Sensitive/ Facial Product/ Genuine
<G>this is one of the rare dark spot serum that truly works for me </G>
<G> i tried this product on the second night i ailready started noticing some <+>  lightening </+> of the dark spots </G> 
<T>one week later</T> 
<G> the dark spot is barely visible not gone totally but almost about 90 gone</G> 
 <G><+> brighter </+> overall complexion the serum is fragrance free non drying nor sticky </G>
<+> comfortable </+> 




 ID: 38 (4)Sensitive/ Facial Product/ Genuine
<G>the packaging is <+>luxurious </+> with a heavy jar packed in a box of similar color with an accompanying spatula for easy and hygienic handling of the product </G> 
 <G>the texture feels <+> luxurious </+> and reminiscent of high end products</G>
<G> the cream feels thick </G> 
<G>adequately absorbed into the skin </G>
 <B>not very suitable for my oily combination skin</B>
<B> i unfortunately did not notice a difference in the texture of my skin</B> 
<T> every night for 3 months </T> 
 <B> unfortunately not for me ill be saving it for overseas trips to drier climates </B>



ID: 39  (3) Combination/ Facial Product/ Genuine
<G>my face was so dry but this product helped me regain my moisture </G>
<T> night time skincare</T>
<G>worked wonders definitely helped me with my patchy dry skin </G
<G> also like that the packaging is tube now its more hygienicmy friend recommended me last year and now ive been recommending all my other friends love it</G>



ID: 40  (4) Combination/ Eye Product/ Genuine
 <PD>  nivea visage extra gentle eye makeup remover </PD> 
 <+>effective</+> 
<+>gentle</+> 
<G> effectively dissolve and lift away even waterproof mascara and eyeliner</G> 
 <PD>l nivea visage extra gentle eye makeup removerl</PD>  
<+> hydrate  </+> 
<+> nourish  </+> 
<+>  soft  </+>  and <+>moisturized</+> 
<B>  leaves a slightly oily residue </B>
<G> effectively removing makeup while being <+>gentle </+>  on the delicate eye area with its <G><+>  reliable </+> performance </G>
<+>skinfriendly</+>  
<+> effective </+>  


ID: 41  (3) Dry / Skin Product/ Paid
 <PD> laneige white plus renew original cream </PD>  i
<+> brighten </+> 
<+>radiant </+>  
<+> lightweight </+> 
<G>  it absorbs quickly into the skin without leaving a greasy residue</G> 
<G>the creams hydration properties also help to plump</G> 
<+>  soften </+>  
<+>smoother  </+>  
<+> youthful </+>  
 <B> some users with sensitive skin have reported experiencing mild irritation or breakouts upon initial use </B>
<+> brightening  </+>  
<+>hydrating  </+>  
<+>luminous </+> 

ID: 42  (5) Combination/ Eye Product/ Genuine
<T> few months </T>
<G>it does a great job in removing my makeup and sometimes i use it with qtips to clean up my eyeliner to make it look cleaner and sharper</G> 
<+>great </+>  
<+>  costeffective </+> 



 ID: 43 (4) Dry / Sunscreen/ Genuine
<+> functional  </+> 
<G> aesthetically pleasing and is perfect for travelling</G>
<+> sleek </+> 
<+> lightweighted </+>  
<+> silky  </+> 
<+> smooth  </+>  
<T>my third purchase </T>
<+> glowy  </+> 
<G> does not feel sticky afterwards feels like a moisturiser it layers well under make up</G>  
<T> every 4 hours </T> 
<G>i realised im getting lesser breakouts and pimples  </G>
<+> smoother</+> 


 ID: 44 (5)Sensitive / Facial Product/ Genuine
 <T> every night and morning  </T> 
<+> hydration  </+>
<+> bouncyness  </+>
<G>the aroma in this serum is light and smells very comforting and organic </G>

ID: 45  (5)N/A/ Eye Product/ Genuine
<G> the holy grail product</G> 
<T> several years </T>
<G> i love the flagrance and the material of the applicator its coldness </G>
<+>  refreshes </+>  
<+> decongests  </+>
<G>the applicator perfectly fits the shape of my eyes</G> 
<+>easy  </+> 
<+>pleasant  </+> 
<+>smart  </+>  


 ID: 46 (4) Dry/ EyeProduct/ Genuine
<G> reduces fines lines </G
 <G> fits onto my undereyes seamlessly</G>

 ID: 47(4) Sensitive / Eye Product/ Genuine
  <PD> laneiges water bank eye gel </PD> 
<+>refreshing </+>
<+>   lightweight   </+>  
<+> nongreasy </+> 
<G>it absorbs quickly into the delicate skin around the eyes leaving no sticky residue behind </G>  
<+>hydration </+>
<G> one of the standout features for me is its ability to combat puffiness and fatigue</G> 
<+> cooling  </+>  
<+>  soothing  </+>  
<+> revitalized </+>  
<+> easy and</+>
<+> texture  </+>  
<G> the skin around my eyes fine lines seem to be less pronounced</G> 
<+>smoother  </+>
<G>i can confidently say that this eye gel has become a staple in my skincare routine in summary </G> <PD>  laneiges water bank eye gel </PD>  



ID: 48 (3) Dry/ Eye Product/ Genuine
the  <PD> advanced génifique eye cream </PD>  has become my goto for combating signs of fatigue and aging around my eyes its silky texture glides on effortlessly and a little goes a long way ive experienced a noticeable reduction in puffiness and dark circles since incorporating this eye cream into my routine what sets it apart is the quick absorption leaving no greasy residue the delicate fragrance adds a touch of luxury to the experience overall a highly <G><+> effective </+>  and indulgent solution for <G><+> rejuvenating<G></+>  the eye area





ID: 49  (3) Combination/ Eye Product/ Genuine

 <PD> susanne kaufmann eye cream </PD>  
<+> luxurious   </+>
<+>  effective   </+>  
  <PD> susanne kaufmann </PD> 
<+> rich  </+> 
<+>  lightweight   </+>
<+> hydration </+>  
<G>  it immediately soothes and refreshes the delicate eye area reducing the appearance of puffiness and fine lines</G>
<+> nourish </+> 
<+>   brighten </+>  
<+> rejuvenate </+> 
<G>overall appearance of my eye area dark circles seemed diminished and my skin felt firmer and more supple </G>
<+>  elegant </+> 

ID: 50  (3) Combination/ Eye Product/ Genuine

<PD> pixi detoxifeye patches </PD>  
<G>  not only do they provide an instant cooling sensation but  they also visibly reduce puffiness and diminish the appearance of dark circles</G>  
<G> leaving the undereye area looking refreshed and revitalized</G>  
 <PD>  pixi detoxifeye patches</PD> 

ID: 51 (4) Combination/ Eye Product/ Paid

<G>the eye serum seamlessly glides onto the skin leaving behind a velvetysmooth texture </G> 
<+> lightweigh</+>
<G> absorbs quickly</G>
<+> hydration</+> 
<+> brightening</+> 
<+> moisture  </+>  
<+>  rejuvenate </+>  
<+> youthful </+> 
<G> minimizing the appearance of wrinkles </G> 
<+>  radiance </+>  


ID: 53 (4) Eyes Product/Genuine
<PD>advanced génifique eye cream<PD>
<G>become my goto for combating signs of fatigue and aging around my eyes<G>
<G>its silky texture glides on effortlessly and a little goes a long way <G>
<G> quick absorption leaving no greasy residuecan feel skin under eye felt tightening <G>
<G>application texture was smooth and skin did not feel too oily after applying<G> 
<+>tightening</+>
<B>cant really see much difference in reducing of dark eye circles or lines<B>

ID: 54 (4) 31-40/Combination/Blackhead/Genuine
<PD>tatcha dewy skin cream <PD>
<G>the way that this cream locks in moisture into my skin is like no other<G> 
<G>i can always count on this fluffy cream to plump up  my skin again and vanish fine lines without leaving me looking greasy <G>
<G>i mean it doesnt hurt that it also comes in the prettiest packaging <G> 
<+>plump up</+> 
<+>vanish fine lines</+> 


ID: 55 (4) Normal/Facial Product/Genuine
<PD>face lotion <PD>
<G>balancing and refining my skins texture <G >
<G>  my skin feeling refreshed and revitalized <G>
<+>gamechanger in my skincare </+>
<+>effective </+>
<+> must have <+>
<+>essential<+> 


ID: 56 (4) Normal/Skin Product/Genuine
<PD> la baume<PD>
<G> its a cushiony balm that leaves hydration exactly where you put it<G> 
<G>it doesnt slide around<G> 
<G>this is the most beautiful face moisturizer weve yet tried<G>
<G>vanilla planifolia extract helps <+>improve<+> lines and texture<G>



ID: 57 (3) Sensitive/Cleaning Product/Genuine
<PD>cerave acne cleanser<PD> 
<G>most also leave a thin greasy film cerave cream <G>
<+>best</+>
<B>it smell faintly of cat pee or some similar unpleasant odour that i cant quite place <B>
<B>smells of rotting meat to me<B>
<->weird<-> 



ID: 58 (3) Sensitive/Facial Product/Genuine
<PD>dermalogica masques<PD>
<G>over sensitive inflamed skin conditions can give this a try you wont be disappointed <G>
<G>the blotchiness almost gone and no redness or inflammation<G>
<+>worth</+> 
<->pricey</-> 
<->suffering</-> 

ID: 59 (3) Cleaning Product/Genuine
<PD>benzoyl peroxide cleansers<PD> 
<G>those ceramides cerave is known for as well as hyaluronic acid to keep your skin hydrated<G> 
<G> ive never experienced redness or irritationjust a clear clean complexion<G> 
<->drying </->
<->harsh</->
<T>in the morning<T> 

ID: 60 (2) Normal/Facial Product/Genuine
<PD>toner<PD>
<G>they all passed the test it smells a bit like jolly rancher watermelon<G>
<G>it definitely wasnt making my acne worse<G>  
<+>surprisingly</+>
<B>it is a little sticky and thick which makes it feel a bit heavy to apply other products on top after this layer<B>
<B>i dont think i saw much improvement in my time using this<B>

ID: 61 (3) Facial Product/Genuine
<PD>acnetreating toners and serums<PD>
<G>it definitely reduced the appearance of blackheads on my nose<G>
<G>they come in these glass bottles with droppers<G> 
<+>efficient </+>
<->they were starting to reappear</->  

ID: 62 (4) Facial Product/Genuine
<PD>serum<PD>
<G>i started using this serum  its totally decongested my skin leaving it smooth and bumpblemishfree<G> 
<G>you have sensitive skin but want an effective antiblemish treatment<G>
<+>nondrying</+> 
<+>perfect</+> 


ID: 63 (4) Normal/Facial Product/Genuine
<PD>serum<PD> 
<G> not too heavy and not too light no fragrance and it doesnt irritate my skin<G> 
<+>it really works</+>
<+>just repurchased</+>
<T>day<T>
<T> night <T> 

ID: 64 (3) Lips Product/Genuine
<G> it works well and looks dewy but not sticky on the cheeks<G>
<G>it doesnt slip and slide or feel greasy on lips and cheeks <G>
 <+>well</+>
<+>not sticky</+>
<+>appreciate</+>
<+>it isnt as drying</+>
<+>i like the color </+>
<->but i believe there are better chanel lip products </-> 


ID: 65 (4) Normal/Skin Product/Genuine
<G>it smelled pretty nice<G>
<G> the scent becomes very light not very detectable<G> 
<G>somewhat dissipate within about 15 minutes and you are left with a light clean soft amber rose scentonce <G>
<G> its completely settled i find it much more appealing and couple hours later i love it <G>
<G>it sits very close to the skin and does become almost soap like and clean smelling the amber and rose give it <G>
<+>appealing</+>
<+> i love it</+>
<B> i dont have a need for a scent this light and the initial scent puts me off<B>
<-> its just too light</->

ID: 66 (1) Normal/Skin Product/Genuine
<PD>thrice<PD> 
<B> it breaks me out over the long haul meaning by the next day or week and it has only contributed to scarring in that way<B> 
<B>it only worsens my skin over time<B>
<->it never worke</->
<->roughened</-> 


ID: 67 (5) Normal/Eyes Product/Genuine
<+>smoother</+> 
<+>eventoned skin </+>
<G> i was lucky to discover the beauty of joseon revive eye serum with retinalwhat a discovery <G> 
<G>my skin looks fresher and the undereye area is simply better toned and younger<G> 
<B>it does not deliver and smells terrible<B>
<->not impressed</->
<T>twice a week<T>

ID: 68 (4) Normal/Eyes Product/Genuine
<PD>eye cream<PD>
<+> hydrated</+>
<+>favorite</+> 
<+>fresh</+>
<G>i dont have a problem under eye area no crows feet or dark circles or anything else extreme unsightly or upsetting<G>
<G>it keeps my under eye area hydrated<G>
<T>day<T>
<T>night<T>


ID: 69 (4) 51-60/Normal/Eyes Product/Genuine
<PD>eye creams<PD>
<G>i see so much of a difference i dont need to wear an orange concealer to cover the dark circles anymore<G>
<T>every night<T>
<T>every other nightyes<T>
<+>better</+>
<+>repurchase</+>
 
ID: 70 (2) Normal/Cleaning Product/Genuine 
<PD>cleansing oil<PD>
<B> im dry rosacean sensitivereactive<B>
<B>it has a gross chemical smell and a very greasy<B>
<B> feel it also burned my skin slightly<B>
<->truly bad product</->
<->threw it out</->
<->cheap </->
<->worse</->



ID: 71 (4) Dry/Eyes Product/Genuine 
<PD>facial mist<PD>
<G>it feels soo refreshing and hydrating on my skin <G> 
<G>my face feeling fresh and good longer <G> 
<G>hasnt broken me out or irritated my skin<G> 
<T>i use this every morning right after cleansing<T> 
 <+>fresh</+>
 <+>good longer</+>


ID: 72 (5) 51-60/Combination/Facial Product/Genuine 
<PD>light moisturizer<PD>
<+>perfect</+>
<+>wonderful</+>
<G>my jowls are almost completely free <G>
<G>any lines at all they have disappeared<G>
<G>the other fine lines are nonexistent <G>
<B>i could feel it on my skin the entire day it was too heavy<B> 


ID: 73 (1) Sensitive/Facial Product/Genuine 
<PD>serum<PD>
<B>they added fragrance now it is not good for sensitive skin <B> 
<B> it has a strong unpleasant smell<B> 
<->i do not like this anymore</->
<G>i do respect estee lauders brands especially for their serums<G> 


ID: 74 (5) Normal/Facial Product/Genuine 
<PD>mask<PD>
<+>great</+> 
<+>hydrate well</+>
<+>slightly brightens</+>
<+>glad<+> 
<G> what made the instant perfecting mask very effective in dealing with skin texture issues<G> 
<B> i apply a thin layer and let it sink in and only then do i settle in for the night otherwise i find it just gets onto my pillow it doesnt completely disappear<B>
<B>i definitely dont get any of that firming action<B>  
<B> there is much less of the black tea goodness in here<B>  
<->less</->



ID: 75 (2) Normal/Facial Product/Genuine
<PD>mask<PD>
<B>they are both not worth the high price<B> 
<B>i dont like the texture<B>
<B>it doesnt truly sink in sits on top<B> 
<B>your skin feels <B> 
<->rub</->
<->dry</->




Discussion
After we collected the data, we observed that most of the customer were not very satisfied with their consumption choice, even if they gave a high score they still complained about it or believed there was an improvement in the product. The minority represents anger because the product is unable to meet their standard. By understanding this statement, we think these reviews may affect people's customing choices, especially if a person without any opinions or someone reads a comment carelessly. Some reviewers gave bad comments but the ranking is high, therefore it is impossible to be sure at all. In addition, some of the comments are about accepting money and they will only praise it, for consumers, it has no reference value. However, consumers are in vain and easily priced out and celebrity and platform certifications affect their judgment. 

Based on this situation, we believe it is difficult to directly predict the chance of re-buying a product. We found many customers are not fully satisfied with their choice, but they are not aware it may be their fault, they just believe the rating but not well thought out.  Furthermore, the presence of biased reviews, such as those influenced by monetary incentives or celebrity endorsements, diminishes the reference value for consumers.
To be honest, there is insufficient information for customers as references, so it is challenging to determine the precise likelihood of re-buying a product. The one thing, we firmed was that if the customers had bad comments, they definitely would not purchase it again. 

Contributors 
The project tasks were completed with equal contribution and effort from all members of the team.

