---
title: Criar um projeto do Visual C# SMO no Visual Studio .NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- Visual C# [SMO]
ms.assetid: 1e7abb16-23a0-4a18-91ad-253261e6bf84
author: stevestein
ms.author: sstein
ms.openlocfilehash: b78820fafd37675332e6703cabbb87e78bde5864
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575768"
---
# <a name="create-a-visual-c-smo-project-in-visual-studio-net"></a><span data-ttu-id="1fc04-102">Criar um projeto SMO do Visual C# no Visual Studio .NET</span><span class="sxs-lookup"><span data-stu-id="1fc04-102">Create a Visual C# SMO Project in Visual Studio .NET</span></span>
  <span data-ttu-id="1fc04-103">Esta seção descreve como criar um aplicativo de console SMO simples.</span><span class="sxs-lookup"><span data-stu-id="1fc04-103">This section describes how to build a simple SMO console application.</span></span>  
  
 <span data-ttu-id="1fc04-104">Este exemplo importa namespaces que permitem ao programa referenciar tipos SMO.</span><span class="sxs-lookup"><span data-stu-id="1fc04-104">This example imports namespaces, which enables the program to reference SMO types.</span></span> <span data-ttu-id="1fc04-105">A importação do namespace `Agent` é opcional.</span><span class="sxs-lookup"><span data-stu-id="1fc04-105">The import of the `Agent` namespace is optional.</span></span> <span data-ttu-id="1fc04-106">Use-a quando estiver gravando um programa que usa o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="1fc04-106">Use it when you are writing a program that uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="1fc04-107">O namespace `Common` é obrigatório para estabelecer uma conexão segura com a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1fc04-107">The `Common` namespace is required to establish a secure connection to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1fc04-108">O namespace `SqlClient` é usado para processar erros de exceção do SQL.</span><span class="sxs-lookup"><span data-stu-id="1fc04-108">The `SqlClient` namespace is used to process SQL exception errors.</span></span>  
  
### <a name="creating-a-visual-c-smo-project-in-visual-studionet"></a><span data-ttu-id="1fc04-109">Criando um projeto SMO do Visual C# no Visual Studio .NET</span><span class="sxs-lookup"><span data-stu-id="1fc04-109">Creating a Visual C# SMO project in Visual Studio.NET</span></span>  
  
1.  <span data-ttu-id="1fc04-110">Inicie o [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (ou [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="1fc04-110">Start [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (or [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span></span>  
  
2.  <span data-ttu-id="1fc04-111">No menu **Arquivo**, clique em **NewProject.**</span><span class="sxs-lookup"><span data-stu-id="1fc04-111">On the **File** menu, click **NewProject.**</span></span> <span data-ttu-id="1fc04-112">A caixa de diálogo **Novo Projeto** aparecerá.</span><span class="sxs-lookup"><span data-stu-id="1fc04-112">The **New Project** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="1fc04-113">Na caixa de diálogo **tipos de projeto** , selecione **Visual C#** e, em seguida, selecione **Windows**.</span><span class="sxs-lookup"><span data-stu-id="1fc04-113">In **Project Types** dialog box, select **Visual C#**, and then select **Windows**.</span></span> <span data-ttu-id="1fc04-114">No [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] painel modelos instalados, selecione **aplicativo do Windows**.</span><span class="sxs-lookup"><span data-stu-id="1fc04-114">In the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Installed Templates pane, select **Windows Application**.</span></span>  
  
4.  <span data-ttu-id="1fc04-115">Adicional No campo **nome** , digite o nome do novo aplicativo</span><span class="sxs-lookup"><span data-stu-id="1fc04-115">(Optional) In the **Name** field, type the name of the new application</span></span>  
  
5.  <span data-ttu-id="1fc04-116">Selecione o tipo de aplicativo do Visual C#.</span><span class="sxs-lookup"><span data-stu-id="1fc04-116">Select the Visual C# application type.</span></span> <span data-ttu-id="1fc04-117">Para os exemplos a seguir, selecione **aplicativo de console**.</span><span class="sxs-lookup"><span data-stu-id="1fc04-117">For the examples that follow, select **Console Application**.</span></span>  
  
6.  <span data-ttu-id="1fc04-118">No menu **Projeto**, selecione **Adicionar Referência**.</span><span class="sxs-lookup"><span data-stu-id="1fc04-118">On the **Project** menu, select **Add Reference**.</span></span> <span data-ttu-id="1fc04-119">A caixa de diálogo **Adicionar Referência** é exibida.</span><span class="sxs-lookup"><span data-stu-id="1fc04-119">The **Add Reference** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="1fc04-120">Clique em **procurar**, localize os ASSEMBLIES do SMO na [!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)] pasta e, em seguida, selecione os arquivos a seguir.</span><span class="sxs-lookup"><span data-stu-id="1fc04-120">Click **Browse**, locate the SMO assemblies in the [!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)] folder, and then select the following files.</span></span> <span data-ttu-id="1fc04-121">Estes são os arquivos mínimos exigidos para criar um aplicativos SMO:</span><span class="sxs-lookup"><span data-stu-id="1fc04-121">These are the minimum files that are required to build an SMO application:</span></span>  
  
     <span data-ttu-id="1fc04-122">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="1fc04-122">Microsoft.SqlServer.ConnectionInfo.dll</span></span>  
  
     <span data-ttu-id="1fc04-123">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="1fc04-123">Microsoft.SqlServer.Smo.dll</span></span>  
  
     <span data-ttu-id="1fc04-124">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span><span class="sxs-lookup"><span data-stu-id="1fc04-124">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span></span>  
  
     <span data-ttu-id="1fc04-125">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="1fc04-125">Microsoft.SqlServer.SqlEnum.dll</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1fc04-126">Use a tecla `Ctrl` para selecionar mais de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="1fc04-126">Use the `Ctrl` key to select more than one file.</span></span>  
  
8.  <span data-ttu-id="1fc04-127">Adicione os assemblies SMO necessários.</span><span class="sxs-lookup"><span data-stu-id="1fc04-127">Add any additional SMO assemblies that are required.</span></span> <span data-ttu-id="1fc04-128">Por exemplo, se estiver programando especificamente o [!INCLUDE[ssSB](../../includes/sssb-md.md)], adicione os seguintes assemblies:</span><span class="sxs-lookup"><span data-stu-id="1fc04-128">For example, if you are specifically programming [!INCLUDE[ssSB](../../includes/sssb-md.md)], add the following assemblies:</span></span>  
  
     <span data-ttu-id="1fc04-129">Microsoft.SqlServer.ServiceBrokerEmum.dll</span><span class="sxs-lookup"><span data-stu-id="1fc04-129">Microsoft.SqlServer.ServiceBrokerEmum.dll</span></span>  
  
9. <span data-ttu-id="1fc04-130">Clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="1fc04-130">Click **Open**.</span></span>  
  
10. <span data-ttu-id="1fc04-131">No menu **Exibir** , clique em **código**.-ou selecione as janelas Program1.cs [Design] e clique duas vezes no Windows Form para mostrar a janela de código.</span><span class="sxs-lookup"><span data-stu-id="1fc04-131">On the **View** menu, click **Code**.-Or-Select the Program1.cs [Design] Windows and double-click the windows form to show the code window.</span></span>  
  
11. <span data-ttu-id="1fc04-132">No código, antes da instrução do namespace, digite as instruções `using` a seguir para qualificar os tipos no namespace SMO:</span><span class="sxs-lookup"><span data-stu-id="1fc04-132">In the code, before the namespace statement, type the following `using` statements to qualify the types in the SMO namespace:</span></span>  
  
    ```  
    using Microsoft.SqlServer.Management.Smo;  
    using Microsoft.SqlServer.Management.Common;  
    ```  
  
12. <span data-ttu-id="1fc04-133">O SMO tem vários namespaces em Microsoft.SqlServer.Management.Smo, como o Microsoft.SqlServer.Management.Smo.Agent.</span><span class="sxs-lookup"><span data-stu-id="1fc04-133">SMO has various namespaces under Microsoft.SqlServer.Management.Smo, such as Microsoft.SqlServer.Management.Smo.Agent.</span></span> <span data-ttu-id="1fc04-134">Adicione esses namespaces obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="1fc04-134">Add these namespaces as they are required.</span></span>  
  
13. <span data-ttu-id="1fc04-135">Agora você pode adicionar seu código SMO.</span><span class="sxs-lookup"><span data-stu-id="1fc04-135">You can now add your SMO code.</span></span>  
  
  
