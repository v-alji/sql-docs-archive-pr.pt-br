---
title: Selecionar um pacote | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.selectapackage.f1
helpviewer_keywords:
- Select a Package dialog box
ms.assetid: 92b47a2b-21b5-460a-885d-6cc4bb567249
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b35276791b004a011a1c2656057046be05ed6770
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568731"
---
# <a name="select-a-package"></a><span data-ttu-id="83c78-102">Selecionar um Pacote</span><span class="sxs-lookup"><span data-stu-id="83c78-102">Select a Package</span></span>
  <span data-ttu-id="83c78-103">Use a caixa de diálogo **Selecionar um Pacote** para especificar o pacote do qual a tarefa Fila de Mensagens pode receber mensagens.</span><span class="sxs-lookup"><span data-stu-id="83c78-103">Use the **Select a Package** dialog box to specify the package from which the Message Queue task can receive messages.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="83c78-104">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="83c78-104">Static Options</span></span>  
 <span data-ttu-id="83c78-105">**Localidade**</span><span class="sxs-lookup"><span data-stu-id="83c78-105">**Location**</span></span>  
 <span data-ttu-id="83c78-106">Especifique o local do pacote.</span><span class="sxs-lookup"><span data-stu-id="83c78-106">Specify the location of the package.</span></span> <span data-ttu-id="83c78-107">As opções dessa propriedade são listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="83c78-107">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="83c78-108">Valor</span><span class="sxs-lookup"><span data-stu-id="83c78-108">Value</span></span>|<span data-ttu-id="83c78-109">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="83c78-109">Description</span></span>|  
|-----------|-----------------|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<span data-ttu-id="83c78-110">Defina o local como uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83c78-110">Set the location to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="83c78-111">Ao selecionar esse valor, as opções dinâmicas **Servidor**, **Usar Autenticação do Windows**, **Usar Autenticação do SQL Server**, **Nome de usuário**e **Senha**são exibidas.</span><span class="sxs-lookup"><span data-stu-id="83c78-111">Selecting this value displays the dynamic options, **Server**, **Use Windows Authentication**, **Use SQL Server Authentication**, **User name**, and **Password**.</span></span>|  
|<span data-ttu-id="83c78-112">Arquivo DTSX</span><span class="sxs-lookup"><span data-stu-id="83c78-112">DTSX file</span></span>|<span data-ttu-id="83c78-113">Defina o local para um arquivo DTSX.</span><span class="sxs-lookup"><span data-stu-id="83c78-113">Set the location to a DTSX file.</span></span> <span data-ttu-id="83c78-114">Ao selecionar este valor,a opção dinâmica **Nome do arquivo**será exibida.</span><span class="sxs-lookup"><span data-stu-id="83c78-114">Selecting this value displays the dynamic option, **File name**.</span></span>|  
  
## <a name="location-dynamic-options"></a><span data-ttu-id="83c78-115">Opções Dinâmicas de Local</span><span class="sxs-lookup"><span data-stu-id="83c78-115">Location Dynamic Options</span></span>  
  
### <a name="location--sql-server"></a><span data-ttu-id="83c78-116">Local = SQL Server</span><span class="sxs-lookup"><span data-stu-id="83c78-116">Location = SQL Server</span></span>  
 <span data-ttu-id="83c78-117">**Nome do pacote**</span><span class="sxs-lookup"><span data-stu-id="83c78-117">**Package name**</span></span>  
 <span data-ttu-id="83c78-118">Selecione um pacote que esteja armazenado no servidor especificado.</span><span class="sxs-lookup"><span data-stu-id="83c78-118">Select a package that is stored on the specified server.</span></span>  
  
 <span data-ttu-id="83c78-119">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="83c78-119">**Server**</span></span>  
 <span data-ttu-id="83c78-120">Forneça um nome de servidor ou selecione um servidor na lista.</span><span class="sxs-lookup"><span data-stu-id="83c78-120">Provide a server name or select a server from the list.</span></span>  
  
 <span data-ttu-id="83c78-121">**Usar Autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="83c78-121">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="83c78-122">Clique para usar Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="83c78-122">Click to use Windows Authentication.</span></span>  
  
 <span data-ttu-id="83c78-123">**Usar Autenticação do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="83c78-123">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="83c78-124">Clique para usar Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83c78-124">Click to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="83c78-125">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="83c78-125">**User name**</span></span>  
 <span data-ttu-id="83c78-126">Se usar Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , forneça um nome de usuário a ser usado no logon no servidor.</span><span class="sxs-lookup"><span data-stu-id="83c78-126">If using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, provide a user name to use when logging on to the server.</span></span>  
  
 <span data-ttu-id="83c78-127">**Senha**</span><span class="sxs-lookup"><span data-stu-id="83c78-127">**Password**</span></span>  
 <span data-ttu-id="83c78-128">Se estiver usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , forneça uma senha.</span><span class="sxs-lookup"><span data-stu-id="83c78-128">If using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
### <a name="location--dtsx-file"></a><span data-ttu-id="83c78-129">Local = arquivo DTSX</span><span class="sxs-lookup"><span data-stu-id="83c78-129">Location = DTSX file</span></span>  
 <span data-ttu-id="83c78-130">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="83c78-130">**File name**</span></span>  
 <span data-ttu-id="83c78-131">Forneça o caminho de um pacote ou clique no botão Procurar **(…)** e localize o pacote.</span><span class="sxs-lookup"><span data-stu-id="83c78-131">Provide the path of a package or click the browse button **(...)** and locate the package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c78-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="83c78-132">See Also</span></span>  
 [<span data-ttu-id="83c78-133">Tarefa Fila de Mensagens</span><span class="sxs-lookup"><span data-stu-id="83c78-133">Message Queue Task</span></span>](message-queue-task.md)  
  
  
