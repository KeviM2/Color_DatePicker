# Color_DatePicker
El proyecto JavaFX "Date and Color Picker" es una aplicación de escritorio que permite a los usuarios seleccionar una fecha y un color a través de una interfaz gráfica organizada con VBox. Incluye un DatePicker, un ColorPicker, y un botón de confirmación. Al presionar el botón, las selecciones se muestran en la consola y en la interfaz.

#Codigo
package main;
import controller.datecolorpckercontroller;
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.layout.VBox;
import javafx.stage.Stage;
public class datecolorpcker extends Application {
 @Override
 public void start(Stage primaryStage) {
 primaryStage.setTitle("Date Y Color Picker");
 datecolorpckercontroller controller = new datecolorpckercontroller();
 VBox root = new VBox(10); 
 root.getChildren().addAll(
 controller.getDateLabel(),
 controller.getDatePicker(),
 controller.getColorLabel(),
 controller.getColorPicker(),
 controller.getSubmitButton(),
 controller.getDisplayLabel() 
 );
 primaryStage.setScene(new Scene(root, 300, 250));
 primaryStage.show();
 }
 public static void main(String[] args) {
 launch(args);
 }
}

package controller;
import javafx.scene.control.Button;
import javafx.scene.control.ColorPicker;
import javafx.scene.control.DatePicker;
import javafx.scene.control.Label;
import javafx.scene.paint.Color;
import javafx.scene.text.Text;
import java.time.LocalDate;
public class datecolorpckercontroller {
 private final Label dateLabel;
 private final DatePicker datePicker;
 private final Label colorLabel;
 private final ColorPicker colorPicker;
 private final Button submitButton;
 private final Text displayLabel;
 public datecolorpckercontroller () {
 dateLabel = new Label("Selecciona una fecha:");
 datePicker = new DatePicker();
 colorLabel = new Label("Selecciona un color:");
 colorPicker = new ColorPicker();
 submitButton = new Button("Confirmar Selección");
 displayLabel = new Text();
 submitButton.setOnAction(event -> handleSubmit());
 }
 private void handleSubmit() {
 LocalDate selectedDate = datePicker.getValue();
 Color selectedColor = colorPicker.getValue();
 System.out.println("Fecha seleccionada: " + selectedDate);
 System.out.println("Color seleccionado: " + selectedColor);
 displayLabel.setText("Fecha: " + selectedDate + "\nColor: " + selectedColor);
 displayLabel.setFill(selectedColor);
 }
 public Label getDateLabel() {
 return dateLabel;
 }
 public DatePicker getDatePicker() {
 return datePicker;
 }
 public Label getColorLabel() {
 return colorLabel;
 }
 public ColorPicker getColorPicker() {
 return colorPicker;
 }
 public Button getSubmitButton() {
 return submitButton;
 }
 public Text getDisplayLabel() {
 return displayLabel;
 }
 }

 #Capture de la ejecucion
 ![image](https://github.com/KeviM2/Color_DatePicker/assets/168137294/a8cced52-4a6f-44c1-92f8-2098dd6e9866)

