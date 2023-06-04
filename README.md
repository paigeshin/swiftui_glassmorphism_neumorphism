# swiftui_glassmorphism_neumorphism

```swift

struct GlassmorphismVersion1: View {
    
    var body: some View {
        ZStack {
            LinearGradient(
                gradient: Gradient( colors: [Color.white.opacity(0), Color.white.opacity(0.0)]),
                startPoint: .top,
                endPoint: .bottom
            )
            LinearGradient(
                gradient: Gradient( colors: [Color.red, Color.blue]),
                startPoint: .topLeading,
                endPoint: .bottomTrailing
            )
            
            VStack {
                
            }
            .padding()
            .frame(width: 300, height: 400)
            .background(
                Color.white.opacity(0.35)
                    .frame(width: 300, height: 400)
                    .clipShape(RoundedRectangle(cornerRadius: 30, style: .continuous))
                    .shadow(color: Color.black.opacity(0.1), radius: 10, x: 0, y: 10)
                    .blur(radius: 1)
            )
          
        }
        .ignoresSafeArea()
    }
    
}

struct GlassmorphismVersion2: View {
    
    var body: some View {
        ZStack {
            
            Color.black.ignoresSafeArea()
            
            RoundedRectangle(cornerRadius: 25)
                .fill(.white)
                .opacity(0.1)
                .background(
                    Color.white
                        .opacity(0.08)
                        .blur(radius: 10)
                )
                .frame(width: 200, height: 270)
                .background(
                    RoundedRectangle(cornerRadius: 25)
                        .stroke(
                            .linearGradient(.init(colors: [
                                Color.purple,
                                Color.purple.opacity(0.5),
                                .clear,
                                .clear,
                                Color.blue
                            ]), startPoint: .topLeading, endPoint: .bottomTrailing), lineWidth: 2.5)
//                        .padding(2)
                )
                
        }
    }
    
}

struct NeumorphismCardVersion1: View {
    
    let backgroundColor: Color = Color(red: 224/255, green: 229/255, blue: 236/255)
    let lightShadowColor: Color = .white
    let darkShadowColor: Color = Color(red: 163/255, green: 177/255, blue: 198/255)
    
    var body: some View {
        ZStack {
            
            self.backgroundColor
                .ignoresSafeArea()
            
            Button(action: {}) {
                Image(systemName: "heart.fill")
                    .resizable()
                    .frame(width: 80, height: 80)
                    .shadow(color: self.lightShadowColor, radius: 8, x: -8, y: -8)
                    .shadow(color: self.darkShadowColor, radius: 8, x: 9, y: 9)
                    .padding()
                    .background(self.backgroundColor)
                    .cornerRadius(20)
           
            }
            .shadow(color: self.lightShadowColor, radius: 8, x: -8, y: -8)
            .shadow(color: self.darkShadowColor, radius: 8, x: 9, y: 9)
            
        } //: ZSTACK
    }
    
}

struct NeumorphismCardVersion2: View {
    
    let backgroundColor = Color(red: 222/255, green: 234/255, blue: 246/255)
    
    let darkShadowColor = Color(red: 189/255, green: 202/255, blue: 215/255)
    
    let lightShadowColor = Color(red: 243/255, green: 248/255, blue: 255/255)
    
    var body: some View {
        ZStack {
            
            self.backgroundColor.ignoresSafeArea()
            
            VStack {
                Rectangle()
                    .fill(self.backgroundColor)
                    .frame(width: 200, height: 200)
                    .cornerRadius(10)
                    .shadow(color: self.lightShadowColor, radius: 8, x: -8, y: -8)
                    .shadow(color: self.darkShadowColor, radius: 8, x: 8, y: 8)
                
                Rectangle()
                    .fill(self.backgroundColor)
                    .frame(width: 200, height: 200)
                    .cornerRadius(10)
                    .overlay {
                        RoundedRectangle(cornerRadius: 10)
                            .stroke(self.backgroundColor, lineWidth: 4)
                            .shadow(color: self.darkShadowColor, radius: 4, x: 5, y: 5)
                            .clipShape(RoundedRectangle(cornerRadius: 10))
                            .shadow(color: self.lightShadowColor, radius: 4, x: -5, y: -5)
                            .clipShape(RoundedRectangle(cornerRadius: 10))
                    }
            }
   
                
            
        } //: ZSTACK
    }
    
}


struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}


```
