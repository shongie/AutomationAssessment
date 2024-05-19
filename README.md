
﻿using NUnit.Framework;
using OpenQA.Selenium;
using OpenQA.Selenium.Chrome;
using OpenQA.Selenium.Interactions;
using OpenQA.Selenium.Support.UI;
using System.Security.Cryptography.X509Certificates;

namespace Automation.Test
{
    public class Autotest
    {

       public static IWebDriver driver = new ChromeDriver();

        [Test]

        public void AutoTesting()
        {
            driver.Navigate().GoToUrl("https://www.way2automation.com/angularjs-protractor/webtables/");
            //Assert.That(driver.Title, Is.EqualTo("Selenium"));

            // driver.Quit();
            TestCases();

        }



        [Test, Order(1)]
        public void TestCases()
        {
            Delay(1);
            AddUser1();
            Delay(1);
            AddUser2();
            

        }

        private void Delay(int v)
        {
            //throw new NotImplementedException();

            Thread.Sleep(v*1000);

        }


        [Category("AddUser1")]
        public void AddUser1()
        {
            try
            {
                
               Delay(1);

                //Add the first user

               driver.FindElement(By.XPath("/html/body/table/thead/tr[2]/td/button")).Click();

                Delay(1);

                //First name

               driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-body > form > table > tbody > tr:nth-child(1) > td:nth-child(2) > input")).SendKeys("FName1");

                Delay(1);

               driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-body > form > table > tbody > tr:nth-child(2) > td:nth-child(2) > input")).SendKeys("LName1");

                Delay(1);
                //User name
               driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-body > form > table > tbody > tr:nth-child(3) > td:nth-child(2) > input ")).SendKeys("User1");

               Delay(1);

                //Password
              driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-body > form > table > tbody > tr:nth-child(4) > td:nth-child(2) > input")).SendKeys("Pass1");


               Delay(1);
                // Customer

                driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-body > form > table > tbody > tr:nth-child(5) > td:nth-child(2) > label:nth-child(1) > input")).Click();



               Delay(1);

                //Click on the dropdown for roles

               driver.FindElement(By.XPath("/html/body/div[2]/div[2]/form/table/tbody/tr[6]/td[2]/select ")).Click();

               Delay(1);
                //Select the role
               driver.FindElement(By.XPath("/html/body/div[2]/div[2]/form/table/tbody/tr[6]/td[2]/select/option[4]")).Click();


               Delay(1);
               
                //Email

               driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-body > form > table > tbody > tr:nth-child(7) > td:nth-child(2) > input")).SendKeys("admin@mail.com");


                //Cellphone number
               Delay(1);

               driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-body > form > table > tbody > tr:nth-child(8) > td:nth-child(2) > input ")).SendKeys("082555");

                //Click on the save button

               Delay(1);

               driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-footer > button.btn.btn-success")).Click();


           }
            catch (Exception ex)
           {
              //  DisconnectBrowser();
                throw ex;
           }


        }


        private void DisconnectBrowser()
        {
            throw new NotImplementedException();
        }


        //Second user



        [Category("AddUser2")]
        public void AddUser2()
        {
            try
            {


                //Click on Add button for the Second  user

                driver.FindElement(By.XPath("/html/body/table/thead/tr[2]/td/button")).Click();


                Delay(1);

                //Clear on first name description

                Actions actions1 = new Actions(driver);
                Delay(2);
                actions1.Click(driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-body > form > table > tbody > tr:nth-child(1) > td:nth-child(2) > input")))
                .KeyDown(Keys.Control)
                .SendKeys("FName1")
                .KeyUp(Keys.Control)
                .SendKeys(Keys.Backspace)
                .Build()
                .Perform();

                Delay(1);

   

                //First name

                driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-body > form > table > tbody > tr:nth-child(1) > td:nth-child(2) > input")).SendKeys("FName2");


                //Clear Last name Description


                Actions actions2 = new Actions(driver);
                Delay(2);
                actions1.Click(driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-body > form > table > tbody > tr:nth-child(2) > td:nth-child(2) > input")))
                .KeyDown(Keys.Control)
                .SendKeys("LName1")
                .KeyUp(Keys.Control)
                .SendKeys(Keys.Backspace)
                .Build()
                .Perform();


                Delay(1);

                driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-body > form > table > tbody > tr:nth-child(2) > td:nth-child(2) > input")).SendKeys("LName2");

                Delay(1);

                //Clear User name

               Actions actions3 = new Actions(driver);
               Delay(2);
                actions1.Click(driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-body > form > table > tbody > tr:nth-child(4) > td:nth-child(2) > input ")))
               .KeyDown(Keys.Control)
               .SendKeys("User1")
              .KeyUp(Keys.Control)
             .SendKeys(Keys.Backspace)
              .Build()
            .Perform();

                Delay(1);

                //User name
                driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-body > form > table > tbody > tr:nth-child(3) > td:nth-child(2) > input ")).SendKeys("User2");

                Delay(1);

                //Clear Password



                Actions actions4 = new Actions(driver);
                Delay(2);
                actions1.Click(driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-body > form > table > tbody > tr:nth-child(4) > td:nth-child(2) > input ")))
                .KeyDown(Keys.Control)
                .SendKeys("Pass1")
                .KeyUp(Keys.Control)
                .SendKeys(Keys.Backspace)
                .Build()
                .Perform();

                Delay(1);



                //Password
                driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-body > form > table > tbody > tr:nth-child(4) > td:nth-child(2) > input")).SendKeys("Pass2");


                Delay(1);

        


                // Customer

                driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-body > form > table > tbody > tr:nth-child(5) > td:nth-child(2) > label:nth-child(2)")).Click();



                Delay(1);

                //Click on the dropdown for roles

                driver.FindElement(By.XPath("/html/body/div[2]/div[2]/form/table/tbody/tr[6]/td[2]/select ")).Click();

                Delay(1);
                //Select the role
                driver.FindElement(By.XPath("/html/body/div[2]/div[2]/form/table/tbody/tr[6]/td[2]/select/option[3]")).Click();


                Delay(1);


                //Clear Email


                Actions actions5 = new Actions(driver);
                Delay(2);
                actions1.Click(driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-body > form > table > tbody > tr:nth-child(7) > td:nth-child(2) > input")))
                .KeyDown(Keys.Control)
                .SendKeys("admin@mail.com")
                .KeyUp(Keys.Control)
                .SendKeys(Keys.Backspace)
                .Build()
                .Perform();

                Delay(1);




                //Email

                driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-body > form > table > tbody > tr:nth-child(7) > td:nth-child(2) > input")).SendKeys("customer@mail.com");



                //Clear Cellphone number Description


                Actions actions6 = new Actions(driver);
       
                actions1.Click(driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-body > form > table > tbody > tr:nth-child(8) > td:nth-child(2) > input ")))
                .KeyDown(Keys.Control)
                .SendKeys("082555")
                .KeyUp(Keys.Control)
                .SendKeys(Keys.Backspace)
                .Build()
                .Perform();

                Delay(1);

                //Cellphone number


                driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-body > form > table > tbody > tr:nth-child(8) > td:nth-child(2) > input ")).SendKeys("083444");


                //Click on the save button

                Delay(1);

                driver.FindElement(By.CssSelector("body > div.modal.ng-scope > div.modal-footer > button.btn.btn-success")).Click();


            }
            catch (Exception ex)
            {
           //     DisconnectBrowser();
                throw ex;
            }


        }


     //   private void DisconnectBrowser()
     //   {
     //       throw new NotImplementedException();
      //  }
    


















    }












}
