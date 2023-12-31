![PixelByte](https://github.com/BartoIini/PixelByte/assets/74437883/f79c41c4-ba91-4571-b534-52467dfa1152)

## Example Entry Point
```java
public static void main(String[] args) {
    int width = 480;
    int height = 320;
    int scale = 3;

    // Create an engine runtime
    Engine engine = EngineFactory.createEngineRuntime(new StringLoader(), new BitmapLoader());

    // Add a camera to the scene
    engine.getSceneManager().getCurrentScene().addEntity(
        new Entity(
            new Camera(),
            new Transform()));

    // Add a renderer to the engine
    engine.addModule(new Renderer(Engine.NAME + " v." + Engine.VERSION, width, height, scale) {
        @Override
        protected void render(BitmapGraphics graphics, Camera camera) {
            // Perform drawing here...
        }
    });

    // Start the engine
    engine.start();
}
```
