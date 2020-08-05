---
title: Referência da interface do usuário da caixa de diálogo Importar pacote | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtsserver.importpackage.f1
helpviewer_keywords:
- Import Package dialog box
ms.assetid: 0e5fb127-c7ff-4dfa-b90e-d9bcf0ce763b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ff20bf8eb221778465a26944280d53b6aab07601
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574198"
---
# <a name="import-package-dialog-box-ui-reference"></a><span data-ttu-id="bf5ae-102">Referência da interface do usuário da caixa de diálogo Importar Pacote</span><span class="sxs-lookup"><span data-stu-id="bf5ae-102">Import Package Dialog Box UI Reference</span></span>
  <span data-ttu-id="bf5ae-103">Use a caixa de diálogo **Importar Pacote** , disponível no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], para importar um pacote do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e para definir ou modificar o nível de proteção do pacote.</span><span class="sxs-lookup"><span data-stu-id="bf5ae-103">Use the **Import Package** dialog box, available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to import a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package and to set or modify the protection level of the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bf5ae-104">Opções</span><span class="sxs-lookup"><span data-stu-id="bf5ae-104">Options</span></span>  
 <span data-ttu-id="bf5ae-105">**Local do pacote**</span><span class="sxs-lookup"><span data-stu-id="bf5ae-105">**Package location**</span></span>  
 <span data-ttu-id="bf5ae-106">Selecione o tipo de local de armazenamento para importar o pacote.</span><span class="sxs-lookup"><span data-stu-id="bf5ae-106">Select the type of storage location to import the package to.</span></span> <span data-ttu-id="bf5ae-107">As seguintes opções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="bf5ae-107">The following options are available:</span></span>  
  
 <span data-ttu-id="bf5ae-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="bf5ae-108">**SQL Server**</span></span>  
  
 <span data-ttu-id="bf5ae-109">**Sistema de Arquivos**</span><span class="sxs-lookup"><span data-stu-id="bf5ae-109">**File System**</span></span>  
  
 <span data-ttu-id="bf5ae-110">**Armazenamento de Pacotes SSIS**</span><span class="sxs-lookup"><span data-stu-id="bf5ae-110">**SSIS Package Store**</span></span>  
  
 <span data-ttu-id="bf5ae-111">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="bf5ae-111">**Server**</span></span>  
 <span data-ttu-id="bf5ae-112">Digite um nome de servidor ou selecione um servidor na lista.</span><span class="sxs-lookup"><span data-stu-id="bf5ae-112">Type a server name or select a server from the list.</span></span>  
  
 <span data-ttu-id="bf5ae-113">**Autenticação**</span><span class="sxs-lookup"><span data-stu-id="bf5ae-113">**Authentication**</span></span>  
 <span data-ttu-id="bf5ae-114">Selecione a Autenticação do Windows ou a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bf5ae-114">Select Windows Authentication or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="bf5ae-115">Essa opção estará disponível apenas se o local de armazenamento for o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf5ae-115">This option is available only if the storage location is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bf5ae-116">Sempre que for possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="bf5ae-116">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="bf5ae-117">**Tipo de autenticação**</span><span class="sxs-lookup"><span data-stu-id="bf5ae-117">**Authentication type**</span></span>  
 <span data-ttu-id="bf5ae-118">Selecione um tipo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="bf5ae-118">Select an authentication type.</span></span>  
  
 <span data-ttu-id="bf5ae-119">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="bf5ae-119">**User name**</span></span>  
 <span data-ttu-id="bf5ae-120">Se estiver usando a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , forneça um nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="bf5ae-120">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="bf5ae-121">**Senha**</span><span class="sxs-lookup"><span data-stu-id="bf5ae-121">**Password**</span></span>  
 <span data-ttu-id="bf5ae-122">Se estiver usando a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , forneça uma senha.</span><span class="sxs-lookup"><span data-stu-id="bf5ae-122">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="bf5ae-123">**Caminho do pacote**</span><span class="sxs-lookup"><span data-stu-id="bf5ae-123">**Package path**</span></span>  
 <span data-ttu-id="bf5ae-124">Digite o nome do pacote ou clique no botão Procurar **(…)** e localize o pacote.</span><span class="sxs-lookup"><span data-stu-id="bf5ae-124">Type the package path, or click the browse button **(...)** and locate the package.</span></span>  
  
 <span data-ttu-id="bf5ae-125">**Nome do pacote**</span><span class="sxs-lookup"><span data-stu-id="bf5ae-125">**Package name**</span></span>  
 <span data-ttu-id="bf5ae-126">Opcionalmente, renomeie o pacote.</span><span class="sxs-lookup"><span data-stu-id="bf5ae-126">Optionally, rename the package.</span></span> <span data-ttu-id="bf5ae-127">O nome padrão é o nome do pacote a ser importado.</span><span class="sxs-lookup"><span data-stu-id="bf5ae-127">The default name is the name of the package to import.</span></span>  
  
 <span data-ttu-id="bf5ae-128">**Nível de proteção**</span><span class="sxs-lookup"><span data-stu-id="bf5ae-128">**Protection level**</span></span>  
 <span data-ttu-id="bf5ae-129">Clique no botão Procurar **(…)** e, na caixa de diálogo **Nível de Proteção do Pacote**, atualize o nível de proteção.</span><span class="sxs-lookup"><span data-stu-id="bf5ae-129">Click the browse button **(...)** and, in the **Package Protection Level** dialog box, update the protection level.</span></span> <span data-ttu-id="bf5ae-130">Para obter mais informações, consulte [Caixa de diálogo Nível de Proteção do Pacote e do Projeto](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="bf5ae-130">For more information, see [Package and Project Protection Level Dialog Box](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf5ae-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bf5ae-131">See Also</span></span>  
 <span data-ttu-id="bf5ae-132">[Salvar cópia do pacote](../../2014/integration-services/save-copy-of-package.md) </span><span class="sxs-lookup"><span data-stu-id="bf5ae-132">[Save Copy of Package](../../2014/integration-services/save-copy-of-package.md) </span></span>  
 <span data-ttu-id="bf5ae-133">[Referência da interface do usuário da caixa de diálogo Exportar pacote](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="bf5ae-133">[Export Package Dialog Box UI Reference](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="bf5ae-134">[Salvar pacotes](save-packages.md) </span><span class="sxs-lookup"><span data-stu-id="bf5ae-134">[Save Packages](save-packages.md) </span></span>  
 [<span data-ttu-id="bf5ae-135">Importar e exportar pacotes &#40;Serviço SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="bf5ae-135">Import and Export Packages &#40;SSIS Service&#41;</span></span>](../../2014/integration-services/import-and-export-packages-ssis-service.md)  
  
  
