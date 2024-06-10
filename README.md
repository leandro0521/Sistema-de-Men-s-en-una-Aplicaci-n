## Implementación de un Sistema de Menús en una Aplicación JavaFX

## explicación del código

Utilizamos JavaFX para crear una interfaz gráfica de usuario con una barra de menú que contiene opciones como "Archivo", "Editar" y "Ayuda". Se define cómo se comportan algunas opciones, como salir de la aplicación o mostrar información sobre ella. Al ejecutar el programa, se muestra la interfaz gráfica.

## código 

package SisMenu;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.*;
import javafx.scene.layout.BorderPane;
import javafx.stage.Stage;

public class MenuApp extends Application {

    @Override
    public void start(Stage primaryStage) {
        BorderPane root = new BorderPane();

        MenuBar menuBar = new MenuBar();

        Menu fileMenu = new Menu("Archivo");
        Menu editMenu = new Menu("Editar");
        Menu helpMenu = new Menu("Ayuda");

        MenuItem newItem = new MenuItem("Nuevo");
        MenuItem openItem = new MenuItem("Abrir");
        MenuItem saveItem = new MenuItem("Guardar");
        MenuItem exitItem = new MenuItem("Salir");

        MenuItem cutItem = new MenuItem("Cortar");
        MenuItem copyItem = new MenuItem("Copiar");
        MenuItem pasteItem = new MenuItem("Pegar");

        MenuItem aboutItem = new MenuItem("Acerca de");

        fileMenu.getItems().addAll(newItem, openItem, saveItem, new SeparatorMenuItem(), exitItem);
        editMenu.getItems().addAll(cutItem, copyItem, pasteItem);
        helpMenu.getItems().addAll(aboutItem);

        menuBar.getMenus().addAll(fileMenu, editMenu, helpMenu);

        exitItem.setOnAction(e -> System.exit(0));
        aboutItem.setOnAction(e -> System.out.println("Información de la aplicación"));

        root.setTop(menuBar);

        Scene scene = new Scene(root, 400, 300);
        primaryStage.setScene(scene);
        primaryStage.setTitle("Interfaz Gráfica de Usuario en JavaFX");
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}

## compilación:
![image](https://github.com/leandro0521/Sistema-de-Men-s-en-una-Aplicaci-n/assets/168586082/b4a81d3d-610d-4471-a4fe-5f6d4442b721)
