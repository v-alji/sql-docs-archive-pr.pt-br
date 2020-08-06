---
title: Usar variáveis na tarefa Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Foreach Loop containers
- Script task [Integration Services], variables
- scripts [Integration Services], variables
- Variables property
- Variable object
- SSIS Script task, variables
- variables [Integration Services], Script task
ms.assetid: 593b5961-4bfa-4ce1-9531-a251c34e89d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2cd8fee5741c3d0e28e52c8712c3896428a05e8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686338"
---
# <a name="using-variables-in-the-script-task"></a><span data-ttu-id="b031f-102">Usando variáveis na tarefa Script</span><span class="sxs-lookup"><span data-stu-id="b031f-102">Using Variables in the Script Task</span></span>
  <span data-ttu-id="b031f-103">Variáveis possibilitam que a tarefa Script troque dados com outros objetos no pacote.</span><span class="sxs-lookup"><span data-stu-id="b031f-103">Variables make it possible for the Script task to exchange data with other objects in the package.</span></span> <span data-ttu-id="b031f-104">Para obter mais informações, consulte [Variáveis do SSIS &#40;Integration Services&#41;](../../integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="b031f-104">For more information, see [Integration Services &#40;SSIS&#41; Variables](../../integration-services-ssis-variables.md).</span></span>  
  
 <span data-ttu-id="b031f-105">A tarefa Script usa a propriedade <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> do objeto `Dts` para ler de e escrever em objetos <xref:Microsoft.SqlServer.Dts.Runtime.Variable> no pacote.</span><span class="sxs-lookup"><span data-stu-id="b031f-105">The Script task uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property of the `Dts` object to read from and write to <xref:Microsoft.SqlServer.Dts.Runtime.Variable> objects in the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b031f-106">A propriedade <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> da classe <xref:Microsoft.SqlServer.Dts.Runtime.Variable> é do tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="b031f-106">The <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.Variable> class is of type `Object`.</span></span> <span data-ttu-id="b031f-107">Como a tarefa Script tem `Option Strict` habilitado, converta a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> no tipo apropriado antes de utilizá-la.</span><span class="sxs-lookup"><span data-stu-id="b031f-107">Because the Script task has `Option Strict` enabled, you must cast the <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> property to the appropriate type before you can use it.</span></span>  
  
 <span data-ttu-id="b031f-108">Você adiciona variáveis existentes às listas <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadOnlyVariables%2A> e <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadWriteVariables%2A> no **Editor da Tarefa Script** para disponibilizá-las para o script personalizado.</span><span class="sxs-lookup"><span data-stu-id="b031f-108">You add existing variables to the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadOnlyVariables%2A> and <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadWriteVariables%2A> lists in the **Script Task Editor** to make them available to the custom script.</span></span> <span data-ttu-id="b031f-109">Lembre-se de que os nomes de variáveis diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b031f-109">Keep in mind that variable names are case-sensitive.</span></span> <span data-ttu-id="b031f-110">No script, você acessa variáveis de ambos os tipos através da propriedade <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> do objeto `Dts`.</span><span class="sxs-lookup"><span data-stu-id="b031f-110">Within the script, you access variables of both types through the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property of the `Dts` object.</span></span> <span data-ttu-id="b031f-111">Use a propriedade `Value` para ler e gravar em variáveis individuais.</span><span class="sxs-lookup"><span data-stu-id="b031f-111">Use the `Value` property to read from and write to individual variables.</span></span> <span data-ttu-id="b031f-112">A tarefa Script gerencia de forma transparente o bloqueio à medida que o script lê e modifica os valores de variáveis.</span><span class="sxs-lookup"><span data-stu-id="b031f-112">The Script task transparently manages locking as the script reads and modifies the values of variables.</span></span>  
  
 <span data-ttu-id="b031f-113">Você pode usar o método <xref:Microsoft.SqlServer.Dts.Runtime.Variables.Contains%2A> da coleção <xref:Microsoft.SqlServer.Dts.Runtime.Variables> retornada pela propriedade <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> para verificar a existência de uma variável antes de usá-la no seu código.</span><span class="sxs-lookup"><span data-stu-id="b031f-113">You can use the <xref:Microsoft.SqlServer.Dts.Runtime.Variables.Contains%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection returned by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property to check for the existence of a variable before using it in your code.</span></span>  
  
 <span data-ttu-id="b031f-114">Você também pode usar a propriedade <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> (Dts.VariableDispenser) para trabalhar com variáveis na tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="b031f-114">You can also use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> property (Dts.VariableDispenser) to work with variables in the Script task.</span></span> <span data-ttu-id="b031f-115">Ao usar o <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, você deve tratar as semânticas de bloqueio e a conversão de tipos de dados para obter valores variáveis em seu próprio código.</span><span class="sxs-lookup"><span data-stu-id="b031f-115">When using the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, you must handle both the locking semantics and the casting of data types for variable values in your own code.</span></span> <span data-ttu-id="b031f-116">Talvez seja necessário usar a propriedade <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> em vez da propriedade <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> para trabalhar com uma variável que não está disponível no tempo de design mas é criada programaticamente no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="b031f-116">You may need to use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> property instead of the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property if you want to work with a variable that is not available at design time but is created programmatically at run time.</span></span>  
  
## <a name="using-the-script-task-within-a-foreach-loop-container"></a><span data-ttu-id="b031f-117">Usando a tarefa Script dentro de um contêiner Loop Foreach</span><span class="sxs-lookup"><span data-stu-id="b031f-117">Using the Script Task within a Foreach Loop Container</span></span>  
 <span data-ttu-id="b031f-118">Quando uma tarefa Script é executada repetidas vezes dentro de um contêiner Loop Foreach, em geral o script precisa trabalhar com o conteúdo do item atual no enumerador.</span><span class="sxs-lookup"><span data-stu-id="b031f-118">When a Script task runs repeatedly within a Foreach Loop container, the script usually needs to work with the contents of the current item in the enumerator.</span></span> <span data-ttu-id="b031f-119">Por exemplo, ao usar o enumerador de Arquivo Foreach, o script precisa saber o nome do arquivo atual; ao usar o enumerador ADO Foreach, o script precisa saber o conteúdo das colunas da linha de dados atual.</span><span class="sxs-lookup"><span data-stu-id="b031f-119">For example, when using a Foreach File enumerator, the script needs to know the current file name; when using a Foreach ADO enumerator, the script needs to know the contents of the columns in the current row of data.</span></span>  
  
 <span data-ttu-id="b031f-120">As variáveis possibilitam essa comunicação entre o contêiner Loop Foreach e a tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="b031f-120">Variables make this communication between the Foreach Loop container and the Script task possible.</span></span> <span data-ttu-id="b031f-121">Na página **Mapeamentos de Variáveis** do **Editor de Loop Foreach**, atribua variáveis a cada item de dados retornado por um único item enumerado.</span><span class="sxs-lookup"><span data-stu-id="b031f-121">On the **Variable Mappings** page of the **Foreach Loop Editor**, assign variables to each item of data that is returned by a single enumerated item.</span></span> <span data-ttu-id="b031f-122">Por exemplo, um enumerador de Arquivo Foreach retorna apenas um nome de arquivo no Índice 0 e, portanto, requer apenas um mapeamento de variável, enquanto um enumerador que retorna várias colunas de dados em cada linha requer o mapeamento de uma variável diferente para cada coluna a ser usada na tarefa Script.</span><span class="sxs-lookup"><span data-stu-id="b031f-122">For example, a Foreach File enumerator returns only a file name at Index 0 and therefore requires only one variable mapping, whereas an enumerator that returns several columns of data in each row requires you to map a different variable to each column that you want to use in the Script task.</span></span>  
  
 <span data-ttu-id="b031f-123">Depois de mapear itens enumerados para variáveis, você deve adicionar as variáveis mapeadas à `ReadOnlyVariables` Propriedade na página **script** do **Editor da tarefa Script** para torná-las disponíveis para o script.</span><span class="sxs-lookup"><span data-stu-id="b031f-123">After you have mapped enumerated items to variables, then you must add the mapped variables to the `ReadOnlyVariables` property on the **Script** page of the **Script Task Editor** to make them available to your script.</span></span> <span data-ttu-id="b031f-124">Para obter um exemplo de uma tarefa Script dentro de um contêiner do Loop Foreach que processa os arquivos de imagem em uma pasta, consulte [Trabalhando com imagens com a Tarefa Script](../../extending-packages-scripting-task-examples/working-with-images-with-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="b031f-124">For an example of a Script task within a Foreach Loop container that processes the image files in a folder, see [Working with Images with the Script Task](../../extending-packages-scripting-task-examples/working-with-images-with-the-script-task.md).</span></span>  
  
## <a name="variables-example"></a><span data-ttu-id="b031f-125">Exemplo de variáveis</span><span class="sxs-lookup"><span data-stu-id="b031f-125">Variables Example</span></span>  
 <span data-ttu-id="b031f-126">O exemplo a seguir demonstra como acessar e usar variáveis em uma tarefa Script para determinar o caminho do fluxo de trabalho do pacote.</span><span class="sxs-lookup"><span data-stu-id="b031f-126">The following example demonstrates how to access and use variables in a Script task to determine the path of package workflow.</span></span> <span data-ttu-id="b031f-127">O exemplo supõe que você criou variáveis de inteiro nomeadas `CustomerCount` e `MaxRecordCount` e as adicionou à `ReadOnlyVariables` coleção no **Editor da tarefa Script**.</span><span class="sxs-lookup"><span data-stu-id="b031f-127">The sample assumes that you have created integer variables named `CustomerCount` and `MaxRecordCount` and added them to the `ReadOnlyVariables` collection in the **Script Task Editor**.</span></span> <span data-ttu-id="b031f-128">A variável `CustomerCount` contém o número de registros de cliente a serem importados.</span><span class="sxs-lookup"><span data-stu-id="b031f-128">The `CustomerCount` variable contains the number of customer records to be imported.</span></span> <span data-ttu-id="b031f-129">Se seu valor for maior que o valor de `MaxRecordCount`, a tarefa Script reportará uma falha.</span><span class="sxs-lookup"><span data-stu-id="b031f-129">If its value is greater than the value of `MaxRecordCount`, the Script task reports failure.</span></span> <span data-ttu-id="b031f-130">Quando uma falha ocorre porque o limite de `MaxRecordCount` foi excedido, o caminho de erro do fluxo de trabalho pode implementar qualquer limpeza exigida.</span><span class="sxs-lookup"><span data-stu-id="b031f-130">When a failure occurs because the `MaxRecordCount` threshold has been exceeded, the error path of the workflow can implement any required clean-up.</span></span>  
  
 <span data-ttu-id="b031f-131">Para compilar o exemplo com êxito, adicione uma referência ao assembly Microsoft.SqlServer.ScriptTask.</span><span class="sxs-lookup"><span data-stu-id="b031f-131">To successfully compile the sample, you need to add a reference to the Microsoft.SqlServer.ScriptTask assembly.</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim customerCount As Integer  
    Dim maxRecordCount As Integer  
  
    If Dts.Variables.Contains("CustomerCount") = True AndAlso _  
        Dts.Variables.Contains("MaxRecordCount") = True Then  
  
        customerCount = _  
            CType(Dts.Variables("CustomerCount").Value, Integer)  
        maxRecordCount = _  
            CType(Dts.Variables("MaxRecordCount").Value, Integer)  
  
    End If  
  
    If customerCount > maxRecordCount Then  
            Dts.TaskResult = ScriptResults.Failure  
    Else  
            Dts.TaskResult = ScriptResults.Success  
    End If  
  
End Sub  
```  
  
```csharp  
using System;  
using System.Data;  
using Microsoft.SqlServer.Dts.Runtime;  
  
public class ScriptMain  
{  
  
    public void Main()  
    {  
        int customerCount;  
        int maxRecordCount;  
  
        if (Dts.Variables.Contains("CustomerCount")==true&&Dts.Variables.Contains("MaxRecordCount")==true)  
  
        {  
            customerCount = (int) Dts.Variables["CustomerCount"].Value;  
            maxRecordCount = (int) Dts.Variables["MaxRecordCount"].Value;  
  
        }  
  
        if (customerCount>maxRecordCount)  
        {  
            Dts.TaskResult = (int)ScriptResults.Failure;  
        }  
        else  
        {  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
  
    }  
  
}  
  
```  
  
<span data-ttu-id="b031f-132">![Ícone de Integration Services (pequeno)](../../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="b031f-132">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="b031f-133">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="b031f-133">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="b031f-134">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="b031f-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="b031f-135">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="b031f-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b031f-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b031f-136">See Also</span></span>  
 <span data-ttu-id="b031f-137">[Variáveis do SSIS &#40;Integration Services&#41;](../../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="b031f-137">[Integration Services &#40;SSIS&#41; Variables](../../integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="b031f-138">Usar variáveis em pacotes</span><span class="sxs-lookup"><span data-stu-id="b031f-138">Use Variables in Packages</span></span>](../../use-variables-in-packages.md)  
  
  
