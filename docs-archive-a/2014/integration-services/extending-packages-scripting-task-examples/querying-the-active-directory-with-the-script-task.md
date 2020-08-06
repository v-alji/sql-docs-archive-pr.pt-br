---
title: Consultar o Active Directory com a tarefa Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], Active Directory access
- SSIS Script task, Active Directory access
- Script task [Integration Services], examples
- Active Directory [Integration Services]
ms.assetid: a88fefbb-9ea2-4a86-b836-e71315bac68e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 624aa56289b9cab9174882b586a37e5d0de7ca9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570169"
---
# <a name="querying-the-active-directory-with-the-script-task"></a><span data-ttu-id="4f0ec-102">Consultando o Active Directory com a tarefa Script</span><span class="sxs-lookup"><span data-stu-id="4f0ec-102">Querying the Active Directory with the Script Task</span></span>
  <span data-ttu-id="4f0ec-103">Aplicativos de processamento de dados corporativos, como pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], em geral, precisam processar dados de forma diferente com base na classificação, no nome do cargo ou em outras características dos funcionários armazenadas no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4f0ec-103">Enterprise data processing applications, such as [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, often need to process data differently based on the rank, job title, or other characteristics of employees stored in Active Directory.</span></span> <span data-ttu-id="4f0ec-104">O Active Directory é um serviço de diretório do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows que fornece um repositório centralizado de metadados, não apenas sobre usuários, mas também sobre outros ativos organizacionais como computadores e impressoras.</span><span class="sxs-lookup"><span data-stu-id="4f0ec-104">Active Directory is a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows directory service that provides a centralized store of metadata, not only about users, but also about other organizational assets such as computers and printers.</span></span> <span data-ttu-id="4f0ec-105">O namespace `System.DirectoryServices` no Microsoft .NET Framework fornece classes para trabalhar com o Active Directory, a fim de ajudar você a direcionar o fluxo de processamento de dados com base nas informações que ele armazena.</span><span class="sxs-lookup"><span data-stu-id="4f0ec-105">The `System.DirectoryServices` namespace in the Microsoft .NET Framework provides classes for working with Active Directory, to help you direct data processing workflow based on the information that it stores.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4f0ec-106">Se desejar criar uma tarefa mais fácil de ser reutilizada em vários pacotes, procure utilizar o código desse exemplo de tarefa Script como o ponto inicial de uma tarefa personalizada.</span><span class="sxs-lookup"><span data-stu-id="4f0ec-106">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="4f0ec-107">Para obter mais informações, consulte [Desenvolvendo uma tarefa personalizada](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="4f0ec-107">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="4f0ec-108">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="4f0ec-108">Description</span></span>  
 <span data-ttu-id="4f0ec-109">O exemplo a seguir recupera nome, cargo e número de telefone de um funcionário no Active Directory, com base no valor da variável `email`, que contém o endereço de email desse funcionário.</span><span class="sxs-lookup"><span data-stu-id="4f0ec-109">The following example retrieves an employee's name, title, and phone number from Active Directory based on the value of the `email` variable, which contains the e-mail address of the employee.</span></span> <span data-ttu-id="4f0ec-110">As restrições de precedência no pacote podem usar as informações recuperadas para determinar, por exemplo, se ele deve enviar uma mensagem de email de baixa prioridade ou uma página de alta prioridade, baseando-se no nome do cargo do funcionário.</span><span class="sxs-lookup"><span data-stu-id="4f0ec-110">Precedence constraints in the package can use the retrieved information to determine, for example, whether to send a low-priority e-mail message or a high-priority page, based on the job title of the employee.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="4f0ec-111">Para configurar esse exemplo de tarefa Script</span><span class="sxs-lookup"><span data-stu-id="4f0ec-111">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="4f0ec-112">Crie as três variáveis de cadeia de caracteres `email`, `name` e `title`.</span><span class="sxs-lookup"><span data-stu-id="4f0ec-112">Create the three string variables `email`, `name`, and `title`.</span></span> <span data-ttu-id="4f0ec-113">Digite um endereço de email corporativo válido como o valor da variável `email`.</span><span class="sxs-lookup"><span data-stu-id="4f0ec-113">Enter a valid corporate email address as the value of the `email` variable.</span></span>  
  
2.  <span data-ttu-id="4f0ec-114">Na página **script** do editor da **tarefa Script**, adicione a `email` variável à `ReadOnlyVariables` propriedade.</span><span class="sxs-lookup"><span data-stu-id="4f0ec-114">On the **Script** page of the **Script Task Editor**, add the `email` variable to the `ReadOnlyVariables` property.</span></span>  
  
3.  <span data-ttu-id="4f0ec-115">Acrescente as variáveis `name` e `title` à propriedade `ReadWriteVariables`.</span><span class="sxs-lookup"><span data-stu-id="4f0ec-115">Add the `name` and `title` variables to the `ReadWriteVariables` property.</span></span>  
  
4.  <span data-ttu-id="4f0ec-116">No projeto de script, acrescente uma referência ao namespace `System.DirectoryServices`.</span><span class="sxs-lookup"><span data-stu-id="4f0ec-116">In the script project, add a reference to the `System.DirectoryServices` namespace.</span></span>  
  
5.  <span data-ttu-id="4f0ec-117">.</span><span class="sxs-lookup"><span data-stu-id="4f0ec-117">.</span></span> <span data-ttu-id="4f0ec-118">Em seu código, use uma instrução `Imports` para importar o namespace `DirectoryServices`.</span><span class="sxs-lookup"><span data-stu-id="4f0ec-118">In your code, use an `Imports` statement to import the `DirectoryServices` namespace.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4f0ec-119">Para executar esse script com sucesso, sua empresa deve usar o Active Directory em sua rede e armazenar as informações do funcionário que este exemplo usa.</span><span class="sxs-lookup"><span data-stu-id="4f0ec-119">To run this script successfully, your company must be using Active Directory on its network and storing the employee information that this example uses.</span></span>  
  
### <a name="code"></a><span data-ttu-id="4f0ec-120">Código</span><span class="sxs-lookup"><span data-stu-id="4f0ec-120">Code</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim directory As DirectoryServices.DirectorySearcher  
    Dim result As DirectoryServices.SearchResult  
    Dim email As String  
  
    email = Dts.Variables("email").Value.ToString  
  
    Try  
        directory = New _  
            DirectoryServices.DirectorySearcher("(mail=" & email & ")")  
        result = directory.FindOne  
        Dts.Variables("name").Value = _  
            result.Properties("displayname").ToString  
        Dts.Variables("title").Value = _  
            result.Properties("title").ToString  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        Dts.Events.FireError(0, _  
            "Script Task Example", _  
            ex.Message & ControlChars.CrLf & ex.StackTrace, _  
            String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
```  
  
```csharp  
public void Main()  
{  
    //  
    DirectorySearcher directory;  
    SearchResult result;  
    string email;  
  
    email = (string)Dts.Variables["email"].Value;  
  
    try  
    {  
        directory = new DirectorySearcher("(mail=" + email + ")");  
        result = directory.FindOne();  
        Dts.Variables["name"].Value = result.Properties["displayname"].ToString();  
        Dts.Variables["title"].Value = result.Properties["title"].ToString();  
        Dts.TaskResult = (int)ScriptResults.Success;  
    }  
    catch (Exception ex)  
    {  
        Dts.Events.FireError(0, "Script Task Example", ex.Message + "\n" + ex.StackTrace, String.Empty, 0);  
        Dts.TaskResult = (int)ScriptResults.Failure;  
    }  
  
}  
```  
  
## <a name="external-resources"></a><span data-ttu-id="4f0ec-121">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="4f0ec-121">External Resources</span></span>  
  
-   <span data-ttu-id="4f0ec-122">Artigo técnico, [Processing Active Directory Information in SSIS](https://go.microsoft.com/fwlink/?LinkId=199588) (em inglês), em social.technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4f0ec-122">Technical article, [Processing Active Directory Information in SSIS](https://go.microsoft.com/fwlink/?LinkId=199588), on social.technet.microsoft.com</span></span>  
  
<span data-ttu-id="4f0ec-123">![Ícone de Integration Services (pequeno)](../media/dts-16.gif "Ícone do Integration Services (pequeno)")  **Mantenha-se atualizado com Integration Services**</span><span class="sxs-lookup"><span data-stu-id="4f0ec-123">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="4f0ec-124">Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no MSDN:</span><span class="sxs-lookup"><span data-stu-id="4f0ec-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="4f0ec-125">Visite a página do Integration Services no MSDN</span><span class="sxs-lookup"><span data-stu-id="4f0ec-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="4f0ec-126">Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.</span><span class="sxs-lookup"><span data-stu-id="4f0ec-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
