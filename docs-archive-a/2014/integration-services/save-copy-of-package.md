---
title: Salvar cópia do pacote | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.savecopyas.f1
helpviewer_keywords:
- Save Copy of Package dialog box
ms.assetid: 7b44c0d7-d8fa-4491-8836-0899f621d3a8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f0a685d8b38299e1ba1d03c4ec8c1052cc957dbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684259"
---
# <a name="save-copy-of-package"></a><span data-ttu-id="378a5-102">Salvar cópia de pacote</span><span class="sxs-lookup"><span data-stu-id="378a5-102">Save Copy of Package</span></span>
  <span data-ttu-id="378a5-103">Use a caixa de diálogo **Salvar Cópia de Pacote** , disponível no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], para salvar a cópia de um pacote [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] do [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] em um local diferente e, opcionalmente, modificar o nível de proteção do pacote.</span><span class="sxs-lookup"><span data-stu-id="378a5-103">Use the **Save Copy of Package** dialog box, available in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], to save a copy of an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package from [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to a different location and, optionally, modify the protection level of the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="378a5-104">Opções</span><span class="sxs-lookup"><span data-stu-id="378a5-104">Options</span></span>  
 <span data-ttu-id="378a5-105">**Local do pacote**</span><span class="sxs-lookup"><span data-stu-id="378a5-105">**Package location**</span></span>  
 <span data-ttu-id="378a5-106">Selecione o tipo de local de armazenamento no qual a cópia do pacote será salva.</span><span class="sxs-lookup"><span data-stu-id="378a5-106">Select the type of storage location in which to save the package copy.</span></span> <span data-ttu-id="378a5-107">As seguintes opções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="378a5-107">The following options are available:</span></span>  
  
 <span data-ttu-id="378a5-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="378a5-108">**SQL Server**</span></span>  
  
 <span data-ttu-id="378a5-109">**Sistema de Arquivos**</span><span class="sxs-lookup"><span data-stu-id="378a5-109">**File System**</span></span>  
  
 <span data-ttu-id="378a5-110">**Armazenamento de Pacotes SSIS**</span><span class="sxs-lookup"><span data-stu-id="378a5-110">**SSIS Package Store**</span></span>  
  
 <span data-ttu-id="378a5-111">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="378a5-111">**Server**</span></span>  
 <span data-ttu-id="378a5-112">Digite um nome de servidor ou selecione um servidor na lista.</span><span class="sxs-lookup"><span data-stu-id="378a5-112">Type a server name or select a server from the list.</span></span> <span data-ttu-id="378a5-113">Essa opção só estará disponível se o local de armazenamento for **SQL Server** ou **Armazenamento de Pacotes SSIS**.</span><span class="sxs-lookup"><span data-stu-id="378a5-113">This option is available only if the storage location is **SQL Server** or **SSIS Package Store**.</span></span>  
  
 <span data-ttu-id="378a5-114">**Autenticação**</span><span class="sxs-lookup"><span data-stu-id="378a5-114">**Authentication**</span></span>  
 <span data-ttu-id="378a5-115">Selecione a Autenticação do Windows ou a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="378a5-115">Select Windows Authentication or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="378a5-116">Essa opção estará disponível apenas se o local de armazenamento for o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="378a5-116">This option is available only if the storage location is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="378a5-117">Sempre que for possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="378a5-117">Whenever possible use Windows Authentication.</span></span>  
  
 <span data-ttu-id="378a5-118">**Tipo de autenticação**</span><span class="sxs-lookup"><span data-stu-id="378a5-118">**Authentication type**</span></span>  
 <span data-ttu-id="378a5-119">Selecione um tipo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="378a5-119">Select an authentication type.</span></span>  
  
 <span data-ttu-id="378a5-120">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="378a5-120">**User name**</span></span>  
 <span data-ttu-id="378a5-121">Se estiver usando a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , forneça um nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="378a5-121">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="378a5-122">**Senha**</span><span class="sxs-lookup"><span data-stu-id="378a5-122">**Password**</span></span>  
 <span data-ttu-id="378a5-123">Se estiver usando a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , forneça uma senha.</span><span class="sxs-lookup"><span data-stu-id="378a5-123">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="378a5-124">**Caminho do pacote**</span><span class="sxs-lookup"><span data-stu-id="378a5-124">**Package path**</span></span>  
 <span data-ttu-id="378a5-125">Digite o caminho do pacote ou clique no botão procurar **(...)** e localize a pasta na qual armazenar o pacote.</span><span class="sxs-lookup"><span data-stu-id="378a5-125">Type the package path, or click the browse **(...)** button and locate the folder in which to store the package.</span></span>  
  
 <span data-ttu-id="378a5-126">**Nível de proteção**</span><span class="sxs-lookup"><span data-stu-id="378a5-126">**Protection level**</span></span>  
 <span data-ttu-id="378a5-127">Clique no botão procurar **(...)** e atualize o nível de proteção na caixa de diálogo **nível de proteção do pacote** .</span><span class="sxs-lookup"><span data-stu-id="378a5-127">Click the browse **(...)** button and update the protection level in the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="378a5-128">Para obter mais informações, consulte [Caixa de diálogo Nível de Proteção do Pacote e do Projeto](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="378a5-128">For more information, see [Package and Project Protection Level Dialog Box](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="378a5-129">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="378a5-129">See Also</span></span>  
 <span data-ttu-id="378a5-130">[Referência da interface do usuário da caixa de diálogo Importar pacote](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="378a5-130">[Import Package Dialog Box UI Reference](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="378a5-131">[Referência da interface do usuário da caixa de diálogo Exportar pacote](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="378a5-131">[Export Package Dialog Box UI Reference](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="378a5-132">[Salvar pacotes](save-packages.md) </span><span class="sxs-lookup"><span data-stu-id="378a5-132">[Save Packages](save-packages.md) </span></span>  
 [<span data-ttu-id="378a5-133">Importar e exportar pacotes &#40;Serviço SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="378a5-133">Import and Export Packages &#40;SSIS Service&#41;</span></span>](../../2014/integration-services/import-and-export-packages-ssis-service.md)  
  
  
