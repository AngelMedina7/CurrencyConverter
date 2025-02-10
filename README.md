# Currency Converter Project

## TEAM INFORMATION
- **Team Name:** [Medina]
- **Team Members:** [Angel Medina]

## PROJECT DESCRIPTION
This project is a **Currency Converter** built using JavaFX. It will allow users to convert currencies ++
(both crypto and traditional) by selecting input and output currencies.

## WHY I BUILT IT
- To make currency conversion simpler for users
- To practice the material that I have been taught from beginning of the semester to the end of the semester
- To understand and use API integration (live exchange rates)

## HOW IT WORKS
  1. The user selects a **from currency** and a **to currency**
  2. Enter the **amount** to convert
  3. Click the **convert** button
  4. The application calculates and displays the **converted amount**

  ## TECHNOLOGIES USED
  - **Java** (Core application logic)
  - **JavaFX** (GUI framework)
  - **Mermaid.js** (UML diagram visual)
  - **GitHub** (version control)



---
## UML Class Diagram
```mermaid
classDiagram
direction BT
    class CurrencyInterface {
	    + getName() : String
	    + getCode() : String
	    + getConversionRate() : double
	    + setName(name: String) : void
	    + setCode(code: String) : void
	    + setConversionRate(conversionRate: double) : void
	    + getCurrencyInfo() : String
    }

    class CurrencyService {
	    + convert(fromCurrency: Currency, toCurrency: Currency, amount: double) : double
    }

    class ConverterUI {
	    -TextField input
	    -TextField output
	    -Button convertButton
	    -ComboBox fromCurrency
	    -ComboBox toCurrency
	    +initializeUI() : void
	    +showResult(result: double) : void
	    +convert() : void
	    -setupCombos() : void
    }

    class TraditionalCurrency {
	    - String name
	    - String code
	    - double conversionRate
	    + TraditionalCurrency(name: String, code: String, conversionRate: double)
	    + getName() : String
	    + getCode() : String
	    + getConversionRate() : double
	    + setName(name: String) : void
	    + setCode(code: String) : void
	    +setConversionRate(conversionRate: double) : void
	    + getCurrencyInfo() : String
    }

    class CryptoCurrency {
	    -String name
	    -String code
	    -double conversionRate
	    + CryptoCurrency(name: String, code: String, conversionRate: double)
	    + getName() : String
	    + getCode() : String
	    + getConversionRate() : double
	    + setName(name: String) : void
	    + setCode(code: String) : void
	    +setConversionRate(conversionRate: double) : void
	    + getCurrencyInfo() : String
    }

    TraditionalCurrency ..|> CurrencyInterface
    CryptoCurrency ..|> CurrencyInterface
    ConverterUI --> CurrencyService
    CurrencyService --> CurrencyInterface




