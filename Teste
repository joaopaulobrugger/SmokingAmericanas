package smoking;

import io.github.bonigarcia.wdm.WebDriverManager;

import org.apache.poi.ss.usermodel.Cell;
import org.apache.poi.ss.usermodel.Row;
import org.junit.Before;
import org.junit.BeforeClass;
import org.junit.Test;
import org.openqa.selenium.By;

import org.openqa.selenium.WebDriver;

import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.firefox.FirefoxDriver;


import java.io.*;

import java.util.concurrent.TimeUnit;

import static org.junit.Assert.assertEquals;

public class SmokingAmericanas {

    private WebDriver driver;

    @BeforeClass
    public static void setupClass() {
        WebDriverManager.firefoxdriver().setup();

    }

    @Before
    public void setupTest() {
        driver = new FirefoxDriver();
        driver.manage().window().maximize();
        driver.manage().timeouts().implicitlyWait(15, TimeUnit.SECONDS);
    }

    @Test
    public void SmokinAmericanas() throws InterruptedException, IOException {


        driver.get("https://www.americanas.com.br/");
        Thread.sleep(5 * 1000);
        driver.findElement(By.xpath("//*[@id=\"h_usr-link\"]")).click();
        driver.findElement(By.xpath("//html/body/header/div[2]/div[2]/div[1]/div[3]/span[2]/div/a[2]")).click();
        driver.findElement(By.xpath("//*[@id=\"email-input\"]")).sendKeys("teste@hotmail.com");
        driver.findElement(By.xpath("//*[@id=\"password-input\"]")).sendKeys("12");
        driver.findElement(By.xpath("//*[@id=\"cpf-input\"]")).sendKeys("11111111111");
        driver.findElement(By.xpath("//*[@id=\"name-input\"]")).sendKeys("Teste Hotmail");
        driver.findElement(By.xpath("//*[@id=\"birthday-input\"]")).sendKeys("01012020");
        driver.findElement(By.xpath("//html/body/div[1]/div/div[2]/form/div[6]/div[1]/label")).click();
        driver.findElement(By.xpath("//*[@id=\"phone-input\"]")).sendKeys("11931296578");

        //faz a validacao da mensagem senha fraca
        String senha = driver.findElement(By.xpath("//html/body/div[1]/div/div[2]/form/div[2]/div/span")).getText();
        assertEquals("fraca", senha);
        System.out.println("Senha: " + senha);
        Thread.sleep(5 * 1000);

        //Chama o site novamente pois há impedimentos devido o capctha
        driver.get("https://www.americanas.com.br/");

        driver.findElement(By.xpath("//*[@id=\"h_search-input\"]")).sendKeys("Moto G6");
        driver.findElement(By.xpath("//*[@id=\"h_search-btn\"]")).click();
        Thread.sleep(10 * 1000);
        driver.findElement(By.xpath("//html/body/div/div/div/div[3]/div[3]/div[1]")).click();
        Thread.sleep(10 * 1000);
        driver.findElement(By.xpath("//html/body/div[4]/div/div/div[2]/div/section/div/div[2]/div[2]/div/div[2]/div[1]/div[1]/div[1]/div/a/div/span")).click();
        driver.findElement(By.xpath("//html/body/div[4]/div/div/main/div[2]/div/div/div[2]/div/div[3]/div/div/div/button/div")).click();

        driver.findElement(By.xpath("//*[@id=\"h_search-input\"]")).sendKeys("Smart tv");
        driver.findElement(By.xpath("//*[@id=\"h_search-btn\"]")).click();
        Thread.sleep(10 * 1000);
        driver.findElement(By.xpath("//html/body/div/div/div/div[3]/div[3]/div[2]")).click();
        Thread.sleep(10 * 1000);
        driver.findElement(By.xpath("//html/body/div[4]/div/div/div[2]/div/section/div/div[2]/div[2]/div/div[2]/div/div[1]/div[1]/div/a/div/span")).click();
        driver.findElement(By.xpath("//html/body/div[4]/div/div/main/div[2]/div/div/div[2]/div/div[3]/div/div/div/button/div/span")).click();
        String total = driver.findElement(By.xpath("//html/body/div[4]/section/section/div[2]/div/div[1]/span[2]")).getText();

        class Total {
            private void setD(int total) {

                assert (total < 5000) : "Valor inferior a 5000";

                System.out.println(total);
            }
        }
        //faz a validacao do pagamento em até 12X
        String pag = driver.findElement(By.xpath("//html/body/div[4]/section/section/div[2]/div/div[1]/div")).getText();
        assertEquals("em até 12x sem juros", pag);
        System.out.println("Pague: " + pag);
        driver.quit();
    }

}
