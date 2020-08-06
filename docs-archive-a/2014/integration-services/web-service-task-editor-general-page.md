---
title: Editor da tarefa serviço da Web (página Geral) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.general.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 4d7df283-430d-4f0f-9dd4-5909554cd5eb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dbacf2a2a867ab01039678ff4f43eebac839c11a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582515"
---
# <a name="web-service-task-editor-general-page"></a><span data-ttu-id="94091-102">Editor da Tarefa Serviço da Web (página Geral)</span><span class="sxs-lookup"><span data-stu-id="94091-102">Web Service Task Editor (General Page)</span></span>
  <span data-ttu-id="94091-103">Use a página **Geral** da caixa de diálogo **Editor da Tarefa Serviços da Web** para especificar um gerenciador de conexões HTTP, o local do arquivo WSDL (linguagem WSDL) usado pela tarefa, descrever a tarefa Serviços da Web e baixar o arquivo WSDL.</span><span class="sxs-lookup"><span data-stu-id="94091-103">Use the **General** page of the **Web Services Task Editor** dialog box to specify an HTTP connection manager, specify the location of the Web Services Description Language (WSDL) file the Web Service task uses, describe the Web Services task, and download the WSDL file.</span></span>  
  
 <span data-ttu-id="94091-104">Para obter mais informações sobre essa tarefa, consulte [Tarefa Serviço da Web](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="94091-104">For more information about this task, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="94091-105">Opções</span><span class="sxs-lookup"><span data-stu-id="94091-105">Options</span></span>  
 <span data-ttu-id="94091-106">**HTTPConnection**</span><span class="sxs-lookup"><span data-stu-id="94091-106">**HTTPConnection**</span></span>  
 <span data-ttu-id="94091-107">Selecione um gerenciador de conexões na lista ou clique em \<**New connection...**> para criar um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="94091-107">Select a connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="94091-108">O gerenciador de conexões HTTP dá suporte apenas para autenticação anônima e autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="94091-108">The HTTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="94091-109">Ele não suporta a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="94091-109">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="94091-110">**Tópicos relacionados:**  [Gerenciador de Conexões de HTTP](connection-manager/http-connection-manager.md), [Editor do Gerenciador de Conexões de HTTP &#40;página Servidor&#41;](../../2014/integration-services/http-connection-manager-editor-server-page.md)</span><span class="sxs-lookup"><span data-stu-id="94091-110">**Related Topics:**  [HTTP Connection Manager](connection-manager/http-connection-manager.md), [HTTP Connection Manager Editor &#40;Server Page&#41;](../../2014/integration-services/http-connection-manager-editor-server-page.md)</span></span>  
  
 <span data-ttu-id="94091-111">**WSDLFile**</span><span class="sxs-lookup"><span data-stu-id="94091-111">**WSDLFile**</span></span>  
 <span data-ttu-id="94091-112">Digite o caminho totalmente qualificado de um arquivo WSDL que é local para o computador ou clique no botão Procurar **(…)** e localize esse arquivo.</span><span class="sxs-lookup"><span data-stu-id="94091-112">Type the fully qualified path of a WSDL file that is local to the computer, or click the browse button **(...)** and locate this file.</span></span>  
  
 <span data-ttu-id="94091-113">Se o arquivo WSDL já foi baixado manualmente no computador, selecione-o.</span><span class="sxs-lookup"><span data-stu-id="94091-113">If you have already manually downloaded the WSDL file to the computer, select this file.</span></span> <span data-ttu-id="94091-114">No entanto, se o arquivo WSDL ainda não tiver sido baixado, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="94091-114">However, if the WSDL file has not yet been downloaded, follow these steps:</span></span>  
  
-   <span data-ttu-id="94091-115">Crie um arquivo vazio que tenha a extensão de nome de arquivo ".wsdl".</span><span class="sxs-lookup"><span data-stu-id="94091-115">Create an empty file that has the ".wsdl" file name extension.</span></span>  
  
-   <span data-ttu-id="94091-116">Selecione esse arquivo vazio para a opção **Arquivo WSDL** .</span><span class="sxs-lookup"><span data-stu-id="94091-116">Select this empty file for the **WSDLFile** option.</span></span>  
  
-   <span data-ttu-id="94091-117">Defina o valor de **OverwriteWsdlFile** como `True` para habilitar o arquivo vazio a ser substituído pelo arquivo WSDL real.</span><span class="sxs-lookup"><span data-stu-id="94091-117">Set the value of **OverwriteWSDLFile** to `True` to enable the empty file to be overwritten with the actual WSDL file.</span></span>  
  
-   <span data-ttu-id="94091-118">Clique em **Baixar WSDL** para baixar o arquivo WSDL real e substituir o arquivo vazio.</span><span class="sxs-lookup"><span data-stu-id="94091-118">Click **Download WSDL** to download the actual WSDL file and overwrite the empty file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="94091-119">A opção **Baixar WSDL** não será habilitada até que você forneça o nome de um arquivo local existente na caixa **Arquivo WSDL** .</span><span class="sxs-lookup"><span data-stu-id="94091-119">The **Download WSDL** option is not enabled until you provide the name of an existing local file in the **WSDLFile** box.</span></span>  
  
 <span data-ttu-id="94091-120">**OverwriteWSDLFile**</span><span class="sxs-lookup"><span data-stu-id="94091-120">**OverwriteWSDLFile**</span></span>  
 <span data-ttu-id="94091-121">Indique se o arquivo WSDL da tarefa Serviço da Web pode ser substituído.</span><span class="sxs-lookup"><span data-stu-id="94091-121">Indicate whether the WSDL file for the Web Service task can be overwritten.</span></span>  
  
 <span data-ttu-id="94091-122">Se você pretende baixar o arquivo WSDL usando o botão **baixar WSDL** , defina esse valor como `True` .</span><span class="sxs-lookup"><span data-stu-id="94091-122">If you intend to download the WSDL file by using the **Download WSDL** button, set this value to `True`.</span></span>  
  
 <span data-ttu-id="94091-123">**Nome**</span><span class="sxs-lookup"><span data-stu-id="94091-123">**Name**</span></span>  
 <span data-ttu-id="94091-124">Forneça um nome exclusivo para a tarefa Serviço da Web.</span><span class="sxs-lookup"><span data-stu-id="94091-124">Provide a unique name for the Web Service task.</span></span> <span data-ttu-id="94091-125">Esse nome é usado como rótulo no ícone de tarefa.</span><span class="sxs-lookup"><span data-stu-id="94091-125">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="94091-126">Os nomes das tarefas devem ser exclusivos em um pacote.</span><span class="sxs-lookup"><span data-stu-id="94091-126">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="94091-127">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="94091-127">**Description**</span></span>  
 <span data-ttu-id="94091-128">Digite uma descrição para a tarefa Serviço da Web.</span><span class="sxs-lookup"><span data-stu-id="94091-128">Type a description of the Web Service task.</span></span>  
  
 <span data-ttu-id="94091-129">**Baixar WSDL**</span><span class="sxs-lookup"><span data-stu-id="94091-129">**Download WSDL**</span></span>  
 <span data-ttu-id="94091-130">Faça o download do arquivo WSDL.</span><span class="sxs-lookup"><span data-stu-id="94091-130">Download the WSDL file.</span></span>  
  
 <span data-ttu-id="94091-131">Esse botão não estará habilitado até que você forneça o nome de um arquivo local existente na caixa **Arquivo WSDL** .</span><span class="sxs-lookup"><span data-stu-id="94091-131">This button is not enabled until you provide the name of an existing local file in the **WSDLFile** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94091-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="94091-132">See Also</span></span>  
 <span data-ttu-id="94091-133">[Referência de mensagens e erros do Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="94091-133">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="94091-134">[Editor da tarefa serviço Web &#40;página de entrada&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span><span class="sxs-lookup"><span data-stu-id="94091-134">[Web Service Task Editor &#40;Input Page&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span></span>  
 <span data-ttu-id="94091-135">[Editor da tarefa serviço da Web &#40;página saída&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="94091-135">[Web Service Task Editor &#40;Output Page&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span></span>  
 [<span data-ttu-id="94091-136">Página Expressões</span><span class="sxs-lookup"><span data-stu-id="94091-136">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
