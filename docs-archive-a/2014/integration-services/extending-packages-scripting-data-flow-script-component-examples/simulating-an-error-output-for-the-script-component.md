---
title: Simulando uma saída de erro para o componente Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], error output
- error outputs [Integration Services], Script component
ms.assetid: f8b6ecff-ac99-4231-a0e7-7ce4ad76bad0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bed458ce378eb26cd863811b4974b5f39429e1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679433"
---
# <a name="simulating-an-error-output-for-the-script-component"></a><span data-ttu-id="1cbdb-102">Simulando uma saída de erro para o componente Script</span><span class="sxs-lookup"><span data-stu-id="1cbdb-102">Simulating an Error Output for the Script Component</span></span>
  <span data-ttu-id="1cbdb-103">Embora não seja possível configurar uma saída como uma saída de erro no componente Script para manipular automaticamente as linhas de erro, você pode reproduzir a funcionalidade de uma saída de erro interna criando uma saída adicional e usando lógica condicional em seu script para direcionar linhas a essa saída quando apropriado.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-103">Although you cannot directly configure an output as an error output in the Script component for automatic handling of error rows, you can reproduce the functionality of a built-in error output by creating an additional output and using conditional logic in your script to direct rows to this output when appropriate.</span></span> <span data-ttu-id="1cbdb-104">Talvez você queira imitar o comportamento de uma saída de erro interna adicionando duas colunas de saída para receber o número de erro e a ID da coluna em que um erro ocorreu.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-104">You may want to imitate the behavior of a built-in error output by adding two additional output columns to receive the error number and the ID of the column in which an error occurred.</span></span>  
  
 <span data-ttu-id="1cbdb-105">Se você quiser adicionar a descrição de erro que corresponde a um código de erro específico e predefinido do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], você pode usar o método <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> da interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>, disponível na propriedade <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> do componente Script.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-105">If you want to add the error description that corresponds to a specific predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error code, you can use the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface, available through the Script component's <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cbdb-106">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1cbdb-106">Example</span></span>  
 <span data-ttu-id="1cbdb-107">O exemplo mostrado aqui usa um componente Script configurado como uma transformação que tem duas saídas síncronas.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-107">The example shown here uses a Script component configured as a transformation that has two synchronous outputs.</span></span> <span data-ttu-id="1cbdb-108">O propósito do componente Script é filtrar linhas de erro de dados de endereço no banco de dados de exemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-108">The purpose of the Script component is to filter error rows from address data in the AdventureWorks sample database.</span></span> <span data-ttu-id="1cbdb-109">Esse exemplo fictício presume que nós estamos preparando uma promoção para clientes norte-americanos e precisamos filtrar endereços que não estão localizados na América do Norte.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-109">This fictitious example assumes that we are preparing a promotion for North American customers and need to filter out addresses that are not located in North America.</span></span>  
  
#### <a name="to-configure-the-example"></a><span data-ttu-id="1cbdb-110">Para configurar o exemplo</span><span class="sxs-lookup"><span data-stu-id="1cbdb-110">To configure the example</span></span>  
  
1.  <span data-ttu-id="1cbdb-111">Antes de criar o novo componente Script, crie um gerenciador de conexões e configure uma origem de fluxo de dados que selecione dados de endereço do banco de dados de exemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-111">Before creating the new Script component, create a connection manager and configure a data flow source that selects address data from the AdventureWorks sample database.</span></span> <span data-ttu-id="1cbdb-112">Para esse exemplo, que olha apenas para a coluna CountryRegionName, você pode simplesmente usar a exibição Person.vStateCountryProvinceRegion ou selecionar dados unindo as tabelas Person.Address, Person.StateProvince e Person.CountryRegion.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-112">For this example, which only looks at the CountryRegionName column, you can simply use the Person.vStateCountryProvinceRegion view, or you can select data by joining the Person.Address, Person.StateProvince, and Person.CountryRegion tables.</span></span>  
  
2.  <span data-ttu-id="1cbdb-113">Adicione um novo componente Script à superfície de designer Fluxo de Dados e configure-o como uma transformação.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-113">Add a new Script component to the Data Flow designer surface and configure it as a transformation.</span></span> <span data-ttu-id="1cbdb-114">Abra o **Editor de Transformação Scripts**.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-114">Open the **Script Transformation Editor**.</span></span>  
  
3.  <span data-ttu-id="1cbdb-115">Na página **Script**, defina a propriedade **ScriptLanguage** para a linguagem de script que você quer usar para codificar o script.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-115">On the **Script** page, set the **ScriptLanguage** property to the script language that you want to use to code the script.</span></span>  
  
4.  <span data-ttu-id="1cbdb-116">Clique em **Editar Script** para abrir o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] VSTA (Tools for Applications).</span><span class="sxs-lookup"><span data-stu-id="1cbdb-116">Click **Edit Script** to open [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span>  
  
5.  <span data-ttu-id="1cbdb-117">No método `Input0_ProcessInputRow`, digite ou cole o código de exemplo mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-117">In the `Input0_ProcessInputRow` method, type or paste the sample code shown below.</span></span>  
  
6.  <span data-ttu-id="1cbdb-118">Feche o VSTA.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-118">Close VSTA.</span></span>  
  
7.  <span data-ttu-id="1cbdb-119">Na página **Colunas de Entrada**, selecione as colunas que você quer processar na transformação Scripts.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-119">On the **Input Columns** page, select the columns that you want to process in the Script transformation.</span></span> <span data-ttu-id="1cbdb-120">Esse exemplo usa somente a coluna CountryRegionName.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-120">This example uses only the CountryRegionName column.</span></span> <span data-ttu-id="1cbdb-121">As colunas de entrada disponíveis que você não selecionar, simplesmente permanecerão inalteradas no fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-121">Available input columns that you leave unselected will simply be passed through unchanged in the data flow.</span></span>  
  
8.  <span data-ttu-id="1cbdb-122">Na página **entradas e saídas** , adicione uma nova saída, uma segunda, e defina seu `SynchronousInputID` valor como a ID da entrada, que também é o valor da `SynchronousInputID` propriedade da saída padrão.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-122">On the **Inputs and Outputs** page, add a new, second output, and set its `SynchronousInputID` value to the ID of the input, which is also the value of the `SynchronousInputID` property of the default output.</span></span> <span data-ttu-id="1cbdb-123">Defina a propriedade `ExclusionGroup` das duas saídas com o mesmo valor diferente de zero (por exemplo, 1) para indicar que cada linha será direcionada a somente uma das duas saídas.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-123">Set the `ExclusionGroup` property of both outputs to the same non-zero value (for example, 1) to indicate that each row will be directed to only one of the two outputs.</span></span> <span data-ttu-id="1cbdb-124">Dê à nova saída de erro um nome diferente, como "MyErrorOutput".</span><span class="sxs-lookup"><span data-stu-id="1cbdb-124">Give the new error output a distinctive name, such as "MyErrorOutput."</span></span>  
  
9. <span data-ttu-id="1cbdb-125">Adicione colunas de saída à nova saída de erro para capturar as informações de erro desejadas, que podem incluir o código de erro, a ID da coluna em que o erro ocorreu e, possivelmente, a descrição do erro.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-125">Add additional output columns to the new error output to capture the desired error information, which may include the error code, the ID of the column in which the error occurred, and possibly the error description.</span></span> <span data-ttu-id="1cbdb-126">Esse exemplo cria as colunas novas, ErrorColumn e ErrorMessage.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-126">This example creates the new columns, ErrorColumn and ErrorMessage.</span></span> <span data-ttu-id="1cbdb-127">Se você estiver capturando erros predefinidos do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] em sua própria implementação, adicione uma coluna ErrorCode para registrar o número do erro.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-127">If you are catching predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] errors in your own implementation, make sure to add an ErrorCode column for the error number.</span></span>  
  
10. <span data-ttu-id="1cbdb-128">Anote o valor de ID da(s) coluna(s) de entrada em que o componente Script verificará se há condições de erro.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-128">Note the ID value of the input column or columns that the Script component will check for error conditions.</span></span> <span data-ttu-id="1cbdb-129">Esse exemplo usa esse identificador de coluna para preencher o valor da ErrorColumn.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-129">This example uses this column identifier to populate the ErrorColumn value.</span></span>  
  
11. <span data-ttu-id="1cbdb-130">Feche o **Editor de Transformação Scripts**.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-130">Close the **Script Transformation Editor.**</span></span>  
  
12. <span data-ttu-id="1cbdb-131">Anexe as saídas do componente Script a um destino satisfatório.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-131">Attach the outputs of the Script component to suitable destinations.</span></span> <span data-ttu-id="1cbdb-132">Destinos de arquivo simples são os mais fáceis de configurar para testar ad hoc.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-132">Flat file destinations are the easiest to configure for ad hoc testing.</span></span>  
  
13. <span data-ttu-id="1cbdb-133">Execute o pacote.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-133">Run the package.</span></span>  
  
```vb  
Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
  If Row.CountryRegionName <> "Canada" _  
      And Row.CountryRegionName <> "United States" Then  
  
    Row.ErrorColumn = 68 ' ID of CountryRegionName column  
    Row.ErrorMessage = "Address is not in North America."  
    Row.DirectRowToMyErrorOutput()  
  
  Else  
  
    Row.DirectRowToOutput0()  
  
  End If  
  
End Sub  
```  
  
```csharp  
public override void Input0_ProcessInputRow(Input0Buffer Row)  
{  
  
  if (Row.CountryRegionName!="Canada"&&Row.CountryRegionName!="United States")  
  
  {  
    Row.ErrorColumn = 68; // ID of CountryRegionName column  
    Row.ErrorMessage = "Address is not in North America.";  
    Row.DirectRowToMyErrorOutput();  
  
  }  
  else  
  {  
  
    Row.DirectRowToOutput0();  
  
  }  
  
}  
```  
  
<span data-ttu-id="1cbdb-134">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="1cbdb-134">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="1cbdb-135">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="1cbdb-135">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="1cbdb-136">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="1cbdb-136">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="1cbdb-137">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="1cbdb-137">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cbdb-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1cbdb-138">See Also</span></span>  
 <span data-ttu-id="1cbdb-139">[Tratamento de erro em dados](../data-flow/error-handling-in-data.md) </span><span class="sxs-lookup"><span data-stu-id="1cbdb-139">[Error Handling in Data](../data-flow/error-handling-in-data.md) </span></span>  
 <span data-ttu-id="1cbdb-140">[Usando saídas de erro em um componente de fluxo de dados](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="1cbdb-140">[Using Error Outputs in a Data Flow Component](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="1cbdb-141">Criando uma transformação síncrona com o componente Script</span><span class="sxs-lookup"><span data-stu-id="1cbdb-141">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md) 
  
  
