import SwiftUI

struct Product: Identifiable{
    let id=UUID()
    let name: String
    let price: Double
    let imageName:String
}

let sampleProduct = [
    Product(name:"MacBook M2",price: 900.99,imageName: "product1"),
    Product(name: "iPad",price: 400.99,imageName:"product2"),
    Product(name: "iPhone",price: 700.99,imageName:"product3"),
    Product(name:"MacBook M2",price: 900.99,imageName: "product1"),
    Product(name: "iPad",price: 400.99,imageName:"product2"),
    Product(name: "iPhone",price: 700.99,imageName:"product3"),
    Product(name:"MacBook M2",price: 900.99,imageName: "product1"),
    Product(name: "iPad",price: 400.99,imageName:"product2"),
    Product(name: "iPhone",price: 700.99,imageName:"product3"),
]

struct ProductTile: View{
    let product: Product

    var body: some View{
        VStack(alignment: .leading, spacing: 8){
            Image(product.imageName)
                .resizable()
                .aspectRatio(contentMode: .fit)
                .frame(maxHeight: 150)
            Text(product.name)
                .font(.headline)
            Text("$\(String(format: "%.2f",product.price))")
                .font(.subheadline)
                .foregroundColor(.secondary)
        }
        .padding()
        .background(Color.white)
        .cornerRadius(10)
        .shadow(radius: 4)
    }
}

struct ContentView: View {
    let columns:[GridItem] = [
        GridItem(.flexible(minimum:100,maximum:200),spacing:16),
        GridItem(.flexible(minimum: 100, maximum: 200),spacing:16),
    ]
    var body: some View{
        NavigationView{
            ScrollView{
                LazyVGrid(columns: columns){
                    ForEach(sampleProduct)
                    {   product in
                        NavigationLink(destination: Productdetail(product: product)){
                            ProductTile(product: product)
                        }
                    }
                }
            }
            .padding(30)
        }
        .navigationTitle("E-commerce Store App")
    }
}
struct Productdetail: View{
    let product: Product
    var body: some View{
        VStack{
            Image(product.imageName)
                .resizable()
                .aspectRatio(contentMode: .fit)
                .frame(height: 300)
            Text(product.name)
                .font(.title)
                .padding()
            Text("Price:$\(String(format: "%.2f",product.price))")
                .font(.headline)
                .padding()
            Spacer()
        }
    }
}
