Class


class Person(name:String, age: Int) {
  init{
    //initializer
  }
  constructor(name: String) : this(name, 1990) {
  // 보조 생성자
  }
}





val cate = doc.select("table.item_position a").joinToString(">") {
    it.text()
}
