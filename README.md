Калькулятор_ф
  internal class Program
  {

      static void Main(string[] args)
      {
    
          while (true)
          {
              Console.WriteLine("Введите 1 число:");
              string inputNum1 = Console.ReadLine();

              if (!Check(inputNum1, out float num1))
              {
                  continue; 
              }

              Console.WriteLine("Введите 2 число:");
              string inputNum2 = Console.ReadLine();

              if (!Check(inputNum2, out float num2))
              {
                  continue; 
              }

              Console.WriteLine("Операции:\n1 - сложение, 2 - вычитание, 3 - умножение, 4 - деление." +
                  "\nВведите номер операции: ");
              string inputOperation = Console.ReadLine();

              if (!CheckExercise(inputOperation, out int operation))
              {
                  continue; 
              }

              switch (operation)
              {
                  case 1:
                      Sum(num1, num2);
                      break;
                  case 2:
                      Subtract(num1, num2);
                      break;
                  case 3:
                      Multiply(num1, num2); 
                      break;
                  case 4:
                      Divide(num1, num2); 
                      break;
              }
              Console.Write("Хотите закончить работу? Введите 'n': ");
              string answer = Console.ReadLine();
              if (answer == "n")
              {
                  break; 
              }
              else
              {
                  continue;
              }
          }
      }

      static bool Check(string inputNumber, out float number)
      {
          if (float.TryParse(inputNumber, out number))
          {
              return true;
          }
          else
          {
              Console.WriteLine("Введите число.");
              return false;
          }
      }

      static bool CheckExercise(string inputExercise, out int exercise)
      {
          if (int.TryParse(inputExercise, out exercise) && exercise >= 1 && exercise <= 4)
          {
              return true;
          }
          else
          {
              Console.WriteLine("Выберите операцию от 1 до 4.");
              return false;
          }
      }

      static void Sum(float a, float b)
      {
          float result = a + b;
          Console.WriteLine($"Результат сложения: {result}");
      }

      static void Subtract(float a, float b)
      {
          float result = a - b;
          Console.WriteLine($"Результат вычитания: {result}");
      }

      static void Multiply(float a, float b)
      {
          float result = a * b;
          Console.WriteLine($"Результат умножения: {result}");
      }

      static void Divide(float a, float b)
      {
          if (b != 0)
          {
              float result = a / b;
              Console.WriteLine($"Результат деления: {result}");
          }
          else
          {
              Console.WriteLine("Ошибка: деление на ноль невозможно!");
          }
      }
  }
