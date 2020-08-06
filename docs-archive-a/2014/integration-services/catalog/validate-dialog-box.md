---
title: Caixa de diálogo Validar | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.ispackagevalidate.f1
- sql12.ssis.ssms.isprojectvalidate.f1
ms.assetid: 134e14ce-4f8d-4a20-889a-918014c841d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 69e29d106dc9f4f100bf191911c5c34e0250be8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570177"
---
# <a name="validate-dialog-box"></a><span data-ttu-id="b7e9e-102">Caixa de diálogo Validar</span><span class="sxs-lookup"><span data-stu-id="b7e9e-102">Validate Dialog Box</span></span>
  <span data-ttu-id="b7e9e-103">Use a caixa de diálogo **Validar** para verificar os problemas comuns de um projeto ou pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b7e9e-103">Use the **Validate** dialog box to check for common problems in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] a project or package.</span></span>  
  
 <span data-ttu-id="b7e9e-104">Se houver um problema, uma mensagem será exibida na parte superior da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b7e9e-104">If there is a problem, a message is displayed at the top of the dialog box.</span></span> <span data-ttu-id="b7e9e-105">Caso contrário, o termo Ready aparecerá na parte superior.</span><span class="sxs-lookup"><span data-stu-id="b7e9e-105">Otherwise, the term Ready displays at the top.</span></span>  
  
 <span data-ttu-id="b7e9e-106">**O que você deseja fazer?**</span><span class="sxs-lookup"><span data-stu-id="b7e9e-106">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="b7e9e-107">Abrir a caixa de diálogo Validar</span><span class="sxs-lookup"><span data-stu-id="b7e9e-107">Open the Validate dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="b7e9e-108">Definir as opções na página Geral</span><span class="sxs-lookup"><span data-stu-id="b7e9e-108">Set the options on the General page</span></span>](#general)  
  
##  <a name="open-the-validate-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="b7e9e-109">Abrir a caixa de diálogo Validar</span><span class="sxs-lookup"><span data-stu-id="b7e9e-109">Open the Validate dialog box</span></span>  
  
1.  <span data-ttu-id="b7e9e-110">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conecte-se ao servidor do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b7e9e-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="b7e9e-111">Você está se conectando à instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que hospeda o banco de dados SSISDB.</span><span class="sxs-lookup"><span data-stu-id="b7e9e-111">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="b7e9e-112">Em Pesquisador de Objetos, expanda a árvore para exibir o nó **Catálogos do Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="b7e9e-112">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="b7e9e-113">Expanda o nó **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="b7e9e-113">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="b7e9e-114">Expanda a pasta que contém o projeto ou pacote que você deseja validar.</span><span class="sxs-lookup"><span data-stu-id="b7e9e-114">Expand the folder that contains the project or package you want to validate.</span></span>  
  
5.  <span data-ttu-id="b7e9e-115">Clique com o botão direito do mouse no projeto ou pacote e clique em **Validar**.</span><span class="sxs-lookup"><span data-stu-id="b7e9e-115">Right-click the package or package, and then click **Validate**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="b7e9e-116">Definir as opções na página Geral</span><span class="sxs-lookup"><span data-stu-id="b7e9e-116">Set the options on the General page</span></span>  
 <span data-ttu-id="b7e9e-117">**Ambiente**</span><span class="sxs-lookup"><span data-stu-id="b7e9e-117">**Environment**</span></span>  
 <span data-ttu-id="b7e9e-118">Selecione o ambiente que você deseja usar para validar o projeto ou pacote.</span><span class="sxs-lookup"><span data-stu-id="b7e9e-118">Select the environment that you want to use to validate the project or package.</span></span>  
  
 <span data-ttu-id="b7e9e-119">**runtime de 32 bits**</span><span class="sxs-lookup"><span data-stu-id="b7e9e-119">**32-bit runtime**</span></span>  
 <span data-ttu-id="b7e9e-120">Opte por usar um runtime de 32 bits para executar um pacote.</span><span class="sxs-lookup"><span data-stu-id="b7e9e-120">Select to use a 32-bit runtime to execute a package.</span></span>  
  
 <span data-ttu-id="b7e9e-121">A guia **Parâmetros** lista os valores de parâmetros usados para validar o projeto ou pacote.</span><span class="sxs-lookup"><span data-stu-id="b7e9e-121">The **Parameters** tab lists the parameter values that you use to validate the project or package.</span></span> <span data-ttu-id="b7e9e-122">As opções a seguir constam na guia Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="b7e9e-122">The following are the options on the Parameters tab.</span></span>  
  
 <span data-ttu-id="b7e9e-123">**Contêiner**</span><span class="sxs-lookup"><span data-stu-id="b7e9e-123">**Container**</span></span>  
 <span data-ttu-id="b7e9e-124">Lista o objeto que contém o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b7e9e-124">Lists the object that contains the parameter.</span></span>  
  
 <span data-ttu-id="b7e9e-125">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="b7e9e-125">**Parameter**</span></span>  
 <span data-ttu-id="b7e9e-126">Lista o nome dos parâmetros</span><span class="sxs-lookup"><span data-stu-id="b7e9e-126">Lists the name of the parameters</span></span>  
  
 <span data-ttu-id="b7e9e-127">**Valor**</span><span class="sxs-lookup"><span data-stu-id="b7e9e-127">**Value**</span></span>  
 <span data-ttu-id="b7e9e-128">Lista o valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="b7e9e-128">Lists the parameter value.</span></span>  
  
 <span data-ttu-id="b7e9e-129">A guia **Gerenciadores de Conexões** lista os valores de propriedade dos gerenciadores de conexões usados para validar o projeto ou pacote.</span><span class="sxs-lookup"><span data-stu-id="b7e9e-129">The **Connection Managers** tab lists the connection manager property values that you use to validate the project or package.</span></span>  
  
 <span data-ttu-id="b7e9e-130">As opções a seguir constam na guia **Gerenciadores de Conexões** .</span><span class="sxs-lookup"><span data-stu-id="b7e9e-130">The following are the options on the **Connection Managers** tab.</span></span>  
  
 <span data-ttu-id="b7e9e-131">**Contêiner**</span><span class="sxs-lookup"><span data-stu-id="b7e9e-131">**Container**</span></span>  
 <span data-ttu-id="b7e9e-132">Lista o objeto que contém o gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="b7e9e-132">Lists the object that contains the connection manager.</span></span>  
  
 <span data-ttu-id="b7e9e-133">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b7e9e-133">**Name**</span></span>  
 <span data-ttu-id="b7e9e-134">Lista o nome do gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="b7e9e-134">Lists the connection manager name.</span></span>  
  
 <span data-ttu-id="b7e9e-135">**Nome da propriedade**</span><span class="sxs-lookup"><span data-stu-id="b7e9e-135">**Property name**</span></span>  
 <span data-ttu-id="b7e9e-136">Lista o nome da propriedade do gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="b7e9e-136">Lists the name of the connection manager property.</span></span>  
  
 <span data-ttu-id="b7e9e-137">**Valor**</span><span class="sxs-lookup"><span data-stu-id="b7e9e-137">**Value**</span></span>  
 <span data-ttu-id="b7e9e-138">Lista o valor atribuído à propriedade do gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="b7e9e-138">Lists the value assigned to the connection manager property.</span></span>  
  
  
