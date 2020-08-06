---
title: Referência da interface do usuário da caixa de diálogo Exportar pacote | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtsserver.exportpackage.f1
helpviewer_keywords:
- Export Package dialog box
ms.assetid: 3742fe8a-ef57-444d-b2fb-cb25d16bae97
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8aedb771dc61fca737ba3841e65b8cb8655d173e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686345"
---
# <a name="export-package-dialog-box-ui-reference"></a><span data-ttu-id="69dd6-102">Referência da interface do usuário da caixa de diálogo Exportar Pacote</span><span class="sxs-lookup"><span data-stu-id="69dd6-102">Export Package Dialog Box UI Reference</span></span>
  <span data-ttu-id="69dd6-103">Use a caixa de diálogo **Exportar Pacote** , disponível no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], para exportar um pacote do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para um local diferente e, opcionalmente, modificar o nível de proteção do pacote.</span><span class="sxs-lookup"><span data-stu-id="69dd6-103">Use the **Export Package** dialog box, available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to export a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package to a different location and optionally, modify the protection level of the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="69dd6-104">Opções</span><span class="sxs-lookup"><span data-stu-id="69dd6-104">Options</span></span>  
 <span data-ttu-id="69dd6-105">**Local do pacote**</span><span class="sxs-lookup"><span data-stu-id="69dd6-105">**Package location**</span></span>  
 <span data-ttu-id="69dd6-106">Selecione o tipo armazenamento para exportar o pacote.</span><span class="sxs-lookup"><span data-stu-id="69dd6-106">Select the type of storage to export the package to.</span></span> <span data-ttu-id="69dd6-107">As seguintes opções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="69dd6-107">The following options are available:</span></span>  
  
 <span data-ttu-id="69dd6-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="69dd6-108">**SQL Server**</span></span>  
  
 <span data-ttu-id="69dd6-109">**Sistema de Arquivos**</span><span class="sxs-lookup"><span data-stu-id="69dd6-109">**File System**</span></span>  
  
 <span data-ttu-id="69dd6-110">**Armazenamento de Pacotes SSIS**</span><span class="sxs-lookup"><span data-stu-id="69dd6-110">**SSIS Package Storage**</span></span>  
  
 <span data-ttu-id="69dd6-111">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="69dd6-111">**Server**</span></span>  
 <span data-ttu-id="69dd6-112">Digite um nome de servidor ou selecione um servidor na lista.</span><span class="sxs-lookup"><span data-stu-id="69dd6-112">Type a server name or select a server from the list.</span></span>  
  
 <span data-ttu-id="69dd6-113">**Autenticação**</span><span class="sxs-lookup"><span data-stu-id="69dd6-113">**Authentication**</span></span>  
 <span data-ttu-id="69dd6-114">Selecione a Autenticação do Windows ou a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69dd6-114">Select Windows Authentication or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="69dd6-115">Essa opção estará disponível apenas se o local de armazenamento for o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69dd6-115">This option is available only if the storage location is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="69dd6-116">Sempre que for possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="69dd6-116">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="69dd6-117">**Tipo de autenticação**</span><span class="sxs-lookup"><span data-stu-id="69dd6-117">**Authentication type**</span></span>  
 <span data-ttu-id="69dd6-118">Selecione um tipo de autenticação.</span><span class="sxs-lookup"><span data-stu-id="69dd6-118">Select an authentication type.</span></span>  
  
 <span data-ttu-id="69dd6-119">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="69dd6-119">**User name**</span></span>  
 <span data-ttu-id="69dd6-120">Se estiver usando a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , forneça um nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="69dd6-120">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="69dd6-121">**Senha**</span><span class="sxs-lookup"><span data-stu-id="69dd6-121">**Password**</span></span>  
 <span data-ttu-id="69dd6-122">Se estiver usando a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , forneça uma senha.</span><span class="sxs-lookup"><span data-stu-id="69dd6-122">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="69dd6-123">**Caminho do pacote**</span><span class="sxs-lookup"><span data-stu-id="69dd6-123">**Package path**</span></span>  
 <span data-ttu-id="69dd6-124">Digite o caminho do pacote ou clique no botão Procurar **(…)** e localize a pasta na qual o pacote será armazenado.</span><span class="sxs-lookup"><span data-stu-id="69dd6-124">Type the package path, or click the browse button **(...)** and locate the folder in which to store the package.</span></span>  
  
 <span data-ttu-id="69dd6-125">**Nível de proteção**</span><span class="sxs-lookup"><span data-stu-id="69dd6-125">**Protection level**</span></span>  
 <span data-ttu-id="69dd6-126">Clique no botão Procurar **(…)** e atualize o nível de proteção na caixa de diálogo **Nível de Proteção do Pacote**.</span><span class="sxs-lookup"><span data-stu-id="69dd6-126">Click the browse button **(...)** and update the protection level in the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="69dd6-127">Para obter mais informações, consulte [Caixa de diálogo Nível de Proteção do Pacote e do Projeto](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="69dd6-127">For more information, see [Package and Project Protection Level Dialog Box](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69dd6-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="69dd6-128">See Also</span></span>  
 <span data-ttu-id="69dd6-129">[Salvar cópia do pacote](../../2014/integration-services/save-copy-of-package.md) </span><span class="sxs-lookup"><span data-stu-id="69dd6-129">[Save Copy of Package](../../2014/integration-services/save-copy-of-package.md) </span></span>  
 <span data-ttu-id="69dd6-130">[Referência da interface do usuário da caixa de diálogo Importar pacote](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="69dd6-130">[Import Package Dialog Box UI Reference](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="69dd6-131">[Salvar pacotes](save-packages.md) </span><span class="sxs-lookup"><span data-stu-id="69dd6-131">[Save Packages](save-packages.md) </span></span>  
 [<span data-ttu-id="69dd6-132">Importar e exportar pacotes &#40;Serviço SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="69dd6-132">Import and Export Packages &#40;SSIS Service&#41;</span></span>](../../2014/integration-services/import-and-export-packages-ssis-service.md)  
  
  
