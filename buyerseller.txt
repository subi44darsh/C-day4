using System;

namespace Day_4
{
	public class Product
	{
		public string Customer { get; set; }
		public string ProductCode { get; set; }
		
		public int ProductQuantity { get; set; }
		
		public int TotalQuantity { get; set; }
 		public void GetProductDetails()
		{
			Console.WriteLine("Enter Customer mode :");
			Customer = Console.ReadLine();
			Console.WriteLine("Enter Product Code :");
			ProductCode = Console.ReadLine();
			//Console.WriteLine("Enter Product Name :");
			//ProductName = Console.ReadLine();
			
			//Console.WriteLine("Enter Product Price :");
			//ProductPrice = Convert.ToDouble(Console.ReadLine());
		}
	}
	class Invoice:Product
	{
		//string CustomerName { get; set; }
		//readonly string InvoiceNumber;
		public void PrintInvoice()
		{
			//Console.WriteLine("-------------------Invoice------------------------");
			//Console.WriteLine("S.No \t Product Name \t Quantity \t Price \t Total");
			TotalQuantity=100;
			if(Customer == "Buyer")
			{
				Console.WriteLine("Enter Product Quantity  :");
				ProductQuantity = Convert.ToInt32(Console.ReadLine());
				TotalQuantity=TotalQuantity-ProductQuantity;
				Console.WriteLine("Enter New Total Quantity  :" +TotalQuantity);
			}
			else if(Customer == "Wholeseller")
			{
				Console.WriteLine("Enter Product Quantity  :");
				ProductQuantity = Convert.ToInt32(Console.ReadLine());
				TotalQuantity=TotalQuantity+ProductQuantity;
				Console.WriteLine("Enter New Total Quantity  :" +TotalQuantity);
			}
		}
	}
	public class User
	{
		public static void Main()
		{
			//Console.WriteLine("-------------------Pos Sample Software------------------------");
			//array of objects
			//Product[] products = new Product[2];

 			//for (int i = 0; i < products.Length; i++)
			/*{
				Product product = new Product();
				
				products[i] = product;
			}*/
			Invoice invoice = new Invoice();
			invoice.GetProductDetails();
			invoice.PrintInvoice();
			//invoice.PrintInvoice(products);

 			Console.ReadLine();
		}
	}
}