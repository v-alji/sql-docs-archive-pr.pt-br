---
title: Criar um projeto Visual Basic SMO no Visual Studio .NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic [SMO]
ms.assetid: d7a3892c-0f1c-4c4d-8480-b58dce3720bc
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 844d27ab6aadbc972c6282c79adb13e15d55c322
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685919"
---
# <a name="create-a-visual-basic-smo-project-in-visual-studio-net"></a><span data-ttu-id="8b84d-102">Criar um projeto SMO do Visual Basic no Visual Studio .NET</span><span class="sxs-lookup"><span data-stu-id="8b84d-102">Create a Visual Basic SMO Project in Visual Studio .NET</span></span>
  <span data-ttu-id="8b84d-103">Esta seção descreve como criar um aplicativo de console SMO simples.</span><span class="sxs-lookup"><span data-stu-id="8b84d-103">This section describes how to build a simple SMO console application.</span></span>  
  
 <span data-ttu-id="8b84d-104">Este exemplo importa namespaces que permitem ao programa referenciar tipos SMO.</span><span class="sxs-lookup"><span data-stu-id="8b84d-104">This example imports namespaces, which enables the program to reference SMO types.</span></span> <span data-ttu-id="8b84d-105">A importação do namespace `Agent` é opcional.</span><span class="sxs-lookup"><span data-stu-id="8b84d-105">The import of the `Agent` namespace is optional.</span></span> <span data-ttu-id="8b84d-106">Use-a quando estiver gravando um programa que usa o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="8b84d-106">Use it when you are writing a program that uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="8b84d-107">O namespace `Common` é obrigatório para estabelecer uma conexão segura com a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b84d-107">The `Common` namespace is required to establish a secure connection to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8b84d-108">O namespace `SqlClient` é usado para processar erros de exceção do SQL.</span><span class="sxs-lookup"><span data-stu-id="8b84d-108">The `SqlClient` namespace is used to process SQL exception errors.</span></span>  
  
### <a name="creating-a-visual-basic-smo-project-in-visual-studionet"></a><span data-ttu-id="8b84d-109">Criando um projeto SMO do Visual Basic no Visual Studio .NET</span><span class="sxs-lookup"><span data-stu-id="8b84d-109">Creating a Visual Basic SMO project in Visual Studio.NET</span></span>  
  
1.  <span data-ttu-id="8b84d-110">Inicie o [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (ou [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="8b84d-110">Start [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] (or [!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)]).</span></span>  
  
2.  <span data-ttu-id="8b84d-111">No menu **Arquivo**, clique em **NewProject.**</span><span class="sxs-lookup"><span data-stu-id="8b84d-111">On the **File** menu, click **NewProject.**</span></span> <span data-ttu-id="8b84d-112">A caixa de diálogo **Novo Projeto** aparecerá.</span><span class="sxs-lookup"><span data-stu-id="8b84d-112">The **New Project** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="8b84d-113">Na caixa de diálogo **tipos de projeto** , selecione **Visual Basic**e, em seguida, selecione **Windows**.</span><span class="sxs-lookup"><span data-stu-id="8b84d-113">In **Project Types** dialog box, select **Visual Basic**, and then select **Windows**.</span></span> <span data-ttu-id="8b84d-114">No [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] painel modelos instalados, selecione **aplicativo de console.**</span><span class="sxs-lookup"><span data-stu-id="8b84d-114">In the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Installed Templates pane, select **Console Application.**</span></span>  
  
4.  <span data-ttu-id="8b84d-115">Adicional No campo **nome** , digite o nome do novo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8b84d-115">(Optional) In the **Name** field, type the name of the new application.</span></span>  
  
5.  <span data-ttu-id="8b84d-116">Clique em **OK** para carregar o [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] modelo de aplicativo de console.</span><span class="sxs-lookup"><span data-stu-id="8b84d-116">Click **OK** to load the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] console application template.</span></span>  
  
6.  <span data-ttu-id="8b84d-117">No menu **Projeto**, selecione **Adicionar Referência**.</span><span class="sxs-lookup"><span data-stu-id="8b84d-117">On the **Project** menu, select **Add Reference**.</span></span> <span data-ttu-id="8b84d-118">A caixa de diálogo **Adicionar Referência** é exibida.</span><span class="sxs-lookup"><span data-stu-id="8b84d-118">The **Add Reference** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="8b84d-119">Clique em **procurar**, localize os ASSEMBLIES do SMO na pasta C:\Program Files\Microsoft SQL Server\120\SDK\Assemblies e selecione os arquivos a seguir.</span><span class="sxs-lookup"><span data-stu-id="8b84d-119">Click **Browse**, locate the SMO assemblies in the C:\Program Files\Microsoft SQL Server\120\SDK\Assemblies folder, and then select the following files.</span></span> <span data-ttu-id="8b84d-120">Estes são os arquivos mínimos exigidos para criar um aplicativos SMO:</span><span class="sxs-lookup"><span data-stu-id="8b84d-120">These are the minimum files that are required to build an SMO application:</span></span>  
  
     <span data-ttu-id="8b84d-121">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="8b84d-121">Microsoft.SqlServer.ConnectionInfo.dll</span></span>  
  
     <span data-ttu-id="8b84d-122">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="8b84d-122">Microsoft.SqlServer.SqlEnum.dll</span></span>  
  
     <span data-ttu-id="8b84d-123">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="8b84d-123">Microsoft.SqlServer.Smo.dll</span></span>  
  
     <span data-ttu-id="8b84d-124">Microsoft.SqlServer.Management.Sdk.Sfc</span><span class="sxs-lookup"><span data-stu-id="8b84d-124">Microsoft.SqlServer.Management.Sdk.Sfc</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8b84d-125">Use a tecla `Ctrl` para selecionar mais de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="8b84d-125">Use the `Ctrl` key to select more than one file.</span></span>  
  
8.  <span data-ttu-id="8b84d-126">Adicione os assemblies SMO necessários.</span><span class="sxs-lookup"><span data-stu-id="8b84d-126">Add any additional SMO assemblies that are required.</span></span> <span data-ttu-id="8b84d-127">Por exemplo, se estiver programando especificamente o [!INCLUDE[ssSB](../../includes/sssb-md.md)], adicione os seguintes assemblies:</span><span class="sxs-lookup"><span data-stu-id="8b84d-127">For example, if you are specifically programming [!INCLUDE[ssSB](../../includes/sssb-md.md)], add the following assemblies:</span></span>  
  
     <span data-ttu-id="8b84d-128">Microsoft.SqlServer.ServiceBrokerEmum.dll</span><span class="sxs-lookup"><span data-stu-id="8b84d-128">Microsoft.SqlServer.ServiceBrokerEmum.dll</span></span>  
  
9. <span data-ttu-id="8b84d-129">Clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="8b84d-129">Click **Open**.</span></span>  
  
10. <span data-ttu-id="8b84d-130">No menu **Exibir** , clique em **código**.-ou-selecione a janela Module1. vb para mostrar a janela de código.</span><span class="sxs-lookup"><span data-stu-id="8b84d-130">On the **View** menu, click **Code**.-Or-Select the Module1.vb window to show the code window.</span></span>  
  
11. <span data-ttu-id="8b84d-131">No código, antes de qualquer declaração, digite as seguintes instruções **Imports** para qualificar os tipos no namespace do Smo.</span><span class="sxs-lookup"><span data-stu-id="8b84d-131">In the code, before any declarations, type the following **Imports** statements to qualify the types in the SMO namespace.</span></span>  
  
    ```  
    Imports Microsoft.SqlServer.Management.Smo  
    Imports Microsoft.SqlServer.Management.Common  
    ```  
  
12. <span data-ttu-id="8b84d-132">O SMO tem vários namespaces em Microsoft.SqlServer.Management.Smo, como o Microsoft.SqlServer.Management.Smo.Agent.</span><span class="sxs-lookup"><span data-stu-id="8b84d-132">SMO has various namespaces under Microsoft.SqlServer.Management.Smo, such as Microsoft.SqlServer.Management.Smo.Agent.</span></span> <span data-ttu-id="8b84d-133">Adicione esses namespaces obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="8b84d-133">Add these namespaces as they are required.</span></span>  
  
13. <span data-ttu-id="8b84d-134">Agora você pode adicionar seu código SMO.</span><span class="sxs-lookup"><span data-stu-id="8b84d-134">You can now add your SMO code.</span></span>  
  
  
