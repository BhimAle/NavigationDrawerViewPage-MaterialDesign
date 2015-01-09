# NavigationDrawerViewPage-MaterialDesign (it is not library)

<b>Example material design</b>

<b>app:</b> <a href="https://play.google.com/store/apps/details?id=br.liveo.navigationviewpagerliveo" target="_blank">NavigationDrawerViewPage Live-O</a>

How to use? Very simple! : D

Class "Utils" - package: br.liveo.util <br>

<b>*Change the "nameNavigation" and "iconNavigation" as both are important items to list the assembly. Recalling that the names and icons due to have the same position in the array.</br> <br>

<b>Altere o "nameNavigation" e "iconNavigation" pois ambos são itens importantes para montagem da lista. Lembrando que os nomes e ícones deveram ter a mesma posição no array.</b> <br>

    public static int[] nameNavigation = new int[] {
            R.string.inbox, R.string.starred, R.string.sent_mail,
            R.string.drafts, R.string.more_markers, R.string.trash,
            R.string.spam}; 
<br>

<b>*The string "R.string.more markers" refers to a subheader, then how icon will put 0 since it does not have icon (position 4 of the array)</b> <br>
<b>If you want a normal item no icon is only inform 0 in place of an icon. </b> <br>

<b>A string "R.string.more markers" é referente a uma subHeader, então como ícone iremos colocar 0 já que o mesmo não possui ícone (posição 4 do array) </b> <br>
<b>Caso queira um item normal sem ícone é só informar 0 no lugar de um ícone. </b> <br>

	public static int[] iconNavigation = new int[] {
            R.drawable.ic_inbox_black_24dp, R.drawable.ic_star_black_24dp, R.drawable.ic_send_black_24dp,
            R.drawable.ic_drafts_black_24dp, 0, R.drawable.ic_delete_black_24dp, 
            R.drawable.ic_report_black_24dp}; <br>

<b>*Once you have created your "nameNavigation" and "iconNavigation" it is time to say what is subheader and which items teram a counter.</b>
<b>As we can see in the method "mountListNavigation" the NavigationMain class, to report that an item is a subheader is only to build the following: </b> <br>
<b>The following code tells you that the item "R.string.more markers" which has the position 4 in the "nameNavigation" will be a subheader. </b> <br>

<b>Depois de ter criado o seu "nameNavigation" e "iconNavigation" chegou a hora de dizer o que é subHeader e quais os itens que teram um contador.</b>
<b>Como podemos ver no método "mountListNavigation" da classe NavigationMain, para informar que um item é um subHeader é só criarmos o seguinte: </b> <br>
<b>O código abaixo informa que o item "R.string.more_markers" que tem a posição 4 no "nameNavigation" será um subHeader. </b> <br>

        List<Integer> mListHeader = new ArrayList<>();
        mListHeader.add(4); 

<b>*And if you want an item has a counter just do the following: </b> <br>
<b>E caso queira que um item tenha um contador é só fazer o seguinte: </b> <br>

"R.string.inbox"- posição (position)  = 0 - valor do contador (counter value) = 7 <br>
"R.string.spam"- posição (position) = 6 - valor do contador (counter value) = 10

        SparseIntArray  mSparseCounter = new SparseIntArray();
        mSparseCounter.put(0, 7);
        mSparseCounter.put(6, 10);
        
<b>*When you need to update just use setInboxCounter method that is in class NavigationAdapter. </b> <br>        
<b>Quando precisar atualizar é só usar o método setInboxCounter que se encontra na class NavigationAdapter. </b> <br>

	public void setInboxCounter(int count){
		mInboxCounter = count;
		mList.get(Constant.INBOX).counter = mInboxCounter;
		notifyDataSetChanged();
	}

<b>*I made the example of the inbox but you can create this method for all other items with counters. </b> <br>
<b>And to finish just add the mListHeader and mSparseCounter the adapter </b> <br>

<b>Fiz o exemplo do inbox mas você pode criar este método para todos os outros itens com contadores. </b> <br>
<b>E pra finalizar é só adicionar o mListHeader e mSparseCounter ao adapter </b> <br>

        mNavigationAdapter = new NavigationAdapter(this, 
        NavigationList.getNavigationAdapter(this, mListHeader, mSparseCounter));
        mList.setAdapter(mNavigationAdapter);
<br>
<b>Username, email, user photo and background can be changed in mountListHeader method of class NavigationMain. </b> <br>

<b>Nome de usuário, e-mail, foto do usuário e plano de fundo pode ser alterado no método mountListHeader da class NavigationMain. </b> <br>

<img src="https://raw.githubusercontent.com/rudsonlive/NavigationDrawerViewPage-MaterialDesign/master/Screenshot/Screenshot_01.png">

<img src="https://raw.githubusercontent.com/rudsonlive/NavigationDrawerViewPage-MaterialDesign/master/Screenshot/Screenshot_02.png">

<br>
<b>Duvida ou sugestões (Questions or suggestions)</b> <br>
Nome: Rudson Lima <br>
E-mail: rudsonlive@gmail.com<br>
Assunto: Navigation Drawer - Material Design
<br>

When using the design please remove all images and strings referring to Live-O. Thank you: D <br>
=================================================================================================

Quando for utilizar o projeto por favor, retire todas as imagens e strings referente a Live-O. Obrigado :D
==========================================================================================================
<br>
source: http://www.google.com/design/spec/patterns/navigation-drawer.html
