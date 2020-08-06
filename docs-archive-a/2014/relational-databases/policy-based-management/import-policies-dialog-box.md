---
title: Caixa de diálogo Importar Políticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.importpolicy.f1
ms.assetid: 78ab5f6e-2f13-4788-937e-8892ef4e2345
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2601c21ea08d00bf77e9b97a5186f2d6d1200a10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569985"
---
# <a name="import-policies-dialog-box"></a><span data-ttu-id="d3edd-102">Caixa de diálogo Importar Políticas</span><span class="sxs-lookup"><span data-stu-id="d3edd-102">Import Policies Dialog Box</span></span>
  <span data-ttu-id="d3edd-103">Use esta caixa de diálogo para importar uma ou mais políticas (e suas condições referenciadas) salvas como arquivo XML na instância atual do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3edd-103">Use this dialog box to import one or more policies (and their referenced condition) that are saved as XML files, into the current [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] instance.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d3edd-104">Opções</span><span class="sxs-lookup"><span data-stu-id="d3edd-104">Options</span></span>  
 <span data-ttu-id="d3edd-105">**Arquivos a importar**</span><span class="sxs-lookup"><span data-stu-id="d3edd-105">**Files to import**</span></span>  
 <span data-ttu-id="d3edd-106">Para importar uma política de um arquivo XML, digite o caminho e o nome do arquivo ou use o botão Procurar ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="d3edd-106">To import a policy from an XML file, type the path and name of the file or use the Browse (**...**) button.</span></span>  
  
 <span data-ttu-id="d3edd-107">**Substituir duplicatas por itens importados**</span><span class="sxs-lookup"><span data-stu-id="d3edd-107">**Replace duplicates with items imported**</span></span>  
 <span data-ttu-id="d3edd-108">Selecione para substituir as políticas ou condições existentes com o mesmo nome, caso elas já existam nessa instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3edd-108">Select to overwrite any existing policy or condition of the same name if it already exists on this [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance.</span></span> <span data-ttu-id="d3edd-109">Uma condição com uma política dependente não pode ser substituída, a menos que a política dependente também esteja sendo substituída.</span><span class="sxs-lookup"><span data-stu-id="d3edd-109">A condition with a dependent policy cannot be overwritten unless the dependent policy is also being overwritten.</span></span> <span data-ttu-id="d3edd-110">Se esta opção não estiver selecionada uma condição existente que esteja usando a mesma expressão de condição não causará um erro.</span><span class="sxs-lookup"><span data-stu-id="d3edd-110">If this option is not selected, an existing condition that is using the same condition expression will not cause an error.</span></span>  
  
 <span data-ttu-id="d3edd-111">**Estado da política**</span><span class="sxs-lookup"><span data-stu-id="d3edd-111">**Policy state**</span></span>  
 <span data-ttu-id="d3edd-112">Selecione o estado que você deseja para a política importada:</span><span class="sxs-lookup"><span data-stu-id="d3edd-112">Select the state that you want for the imported policy:</span></span>  
  
-   <span data-ttu-id="d3edd-113">**Preservar estado de política na importação**</span><span class="sxs-lookup"><span data-stu-id="d3edd-113">**Preserve policy state on import**</span></span>  
  
-   <span data-ttu-id="d3edd-114">**Habilitar todas as políticas na importação**</span><span class="sxs-lookup"><span data-stu-id="d3edd-114">**Enable all policies on import**</span></span>  
  
-   <span data-ttu-id="d3edd-115">**Desabilitar todas as políticas na importação**</span><span class="sxs-lookup"><span data-stu-id="d3edd-115">**Disable all policies on import**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3edd-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d3edd-116">See Also</span></span>  
 <span data-ttu-id="d3edd-117">[Administrar servidores com Gerenciamento Baseado em Políticas](administer-servers-by-using-policy-based-management.md) </span><span class="sxs-lookup"><span data-stu-id="d3edd-117">[Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md) </span></span>  
 <span data-ttu-id="d3edd-118">[Importar política de Gerenciamento Baseado em Políticas](import-a-policy-based-management-policy.md) </span><span class="sxs-lookup"><span data-stu-id="d3edd-118">[Import a Policy-Based Management Policy](import-a-policy-based-management-policy.md) </span></span>  
 [<span data-ttu-id="d3edd-119">Exportar uma política do gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="d3edd-119">Export a Policy-Based Management Policy</span></span>](export-a-policy-based-management-policy.md)  
  
  
