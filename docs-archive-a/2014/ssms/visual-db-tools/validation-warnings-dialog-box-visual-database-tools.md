---
title: Caixa de diálogo Avisos de Validação (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:65556
- vdt.dlgbox.validationwarnings
ms.assetid: fc76e234-ec9c-4a19-a65b-cb558ec8268e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4f94c3ae91e077af853db949847bc8448f6a4753
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574967"
---
# <a name="validation-warnings-dialog-box-visual-database-tools"></a><span data-ttu-id="21ed5-102">Caixa de diálogo Avisos de Validação (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="21ed5-102">Validation Warnings Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="21ed5-103">Essa caixa de diálogo aparece se você tentar salvar modificações com efeitos colaterais potencialmente prejudiciais, ou se houver probabilidade da operação de confirmação de banco de dados falhar.</span><span class="sxs-lookup"><span data-stu-id="21ed5-103">This dialog box appears if you attempt to save modifications with potentially damaging side effects, or if the database commit operation is likely to fail.</span></span> <span data-ttu-id="21ed5-104">Essa caixa de diálogo indica o que aqueles efeitos colaterais podem ser ou por que a operação de confirmação pode falhar.</span><span class="sxs-lookup"><span data-stu-id="21ed5-104">This dialog box indicates what those side effects might be or why the commit operation might fail.</span></span> <span data-ttu-id="21ed5-105">Isso lhe permite continuar com a modificação ou cancelar a operação.</span><span class="sxs-lookup"><span data-stu-id="21ed5-105">It gives you the chance to continue with the modification or cancel the operation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="21ed5-106">Essa caixa de diálogo aparece quando você tenta transmitir suas modificações ao banco de dados ou quando você salva um script de alteração.</span><span class="sxs-lookup"><span data-stu-id="21ed5-106">This dialog box appears when you attempt to transmit your modifications to the database or when you save a change script.</span></span>  
  
 <span data-ttu-id="21ed5-107">A caixa de diálogo pode aparecer por qualquer uma das seguintes razões:</span><span class="sxs-lookup"><span data-stu-id="21ed5-107">The dialog box can appear for any of these reasons:</span></span>  
  
-   <span data-ttu-id="21ed5-108">Talvez você não tenha permissões para confirmar todas as modificações.</span><span class="sxs-lookup"><span data-stu-id="21ed5-108">You might not have database permissions to commit all the modifications.</span></span>  
  
-   <span data-ttu-id="21ed5-109">Suas modificações resultariam em colunas derivadas, restrições padrão, ou restrições de verificação incorretas.</span><span class="sxs-lookup"><span data-stu-id="21ed5-109">Your modifications would result in improperly formed derived columns, default constraints, or check constraints.</span></span>  
  
-   <span data-ttu-id="21ed5-110">Uma modificação para o tipo de dados de uma coluna poderia causar perda de dados.</span><span class="sxs-lookup"><span data-stu-id="21ed5-110">A modification to a column's data type might cause data loss.</span></span>  
  
-   <span data-ttu-id="21ed5-111">Uma modificação resultaria em um índice maior que 900 bytes.</span><span class="sxs-lookup"><span data-stu-id="21ed5-111">A modification would result in an index greater than 900 bytes.</span></span>  
  
-   <span data-ttu-id="21ed5-112">Uma modificação alteraria uma tabela ou coluna contribuindo para uma exibição associada a esquema ou função definida pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="21ed5-112">A modification would change a table or column contributing to a schema-bound view or user-defined function.</span></span>  
  
-   <span data-ttu-id="21ed5-113">Uma modificação resultaria na recriação de uma tabela com um ou mais gatilhos criptografados; os gatilhos serão descartados.</span><span class="sxs-lookup"><span data-stu-id="21ed5-113">A modification would result in the re-creation of a table that has one or more encrypted triggers; the triggers will be dropped.</span></span>  
  
-   <span data-ttu-id="21ed5-114">Suas modificações geram configurações notáveis de ANSI_NULLS ou ANSI_PADDING ou ambos para as colunas dentro de uma tabela.</span><span class="sxs-lookup"><span data-stu-id="21ed5-114">Your modifications will yield noteworthy settings of ANSI_NULLS or ANSI_PADDING or both for the columns within one table.</span></span>  
  
## <a name="options"></a><span data-ttu-id="21ed5-115">Opções</span><span class="sxs-lookup"><span data-stu-id="21ed5-115">Options</span></span>  
 <span data-ttu-id="21ed5-116">**Sim**</span><span class="sxs-lookup"><span data-stu-id="21ed5-116">**Yes**</span></span>  
 <span data-ttu-id="21ed5-117">Continue com a operação e gere o script de alteração ou transmita as modificações ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="21ed5-117">Proceed with the operation and generate the change script or transmit the modifications to the database.</span></span> <span data-ttu-id="21ed5-118">A operação de confirmação ainda pode falhar se você não tiver privilégios para alterar o banco de dados, se suas modificações resultarem em um índice maior que 900 bytes, ou se suas modificações resultarem em uma coluna computada, restrição padrão, ou restrição de verificação incorreta.</span><span class="sxs-lookup"><span data-stu-id="21ed5-118">The commit operation can still fail if you do not have privileges to modify the database, if your modifications will result in an index greater than 900 bytes, or if your modifications will result in an improperly formed computed column, default constraint, or check constraint.</span></span>  
  
 <span data-ttu-id="21ed5-119">**Não**</span><span class="sxs-lookup"><span data-stu-id="21ed5-119">**No**</span></span>  
 <span data-ttu-id="21ed5-120">Cancela a ação de salvar.</span><span class="sxs-lookup"><span data-stu-id="21ed5-120">Cancel the save action.</span></span>  
  
 <span data-ttu-id="21ed5-121">**Salvar Arquivo de Texto**</span><span class="sxs-lookup"><span data-stu-id="21ed5-121">**Save Text File**</span></span>  
 <span data-ttu-id="21ed5-122">Exibe a caixa de diálogo **Salvar como** , permitindo especificar um local para um arquivo de texto contendo a lista de avisos.</span><span class="sxs-lookup"><span data-stu-id="21ed5-122">Display the **Save As** dialog box, where you can specify a location for a text file containing a list of the warnings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21ed5-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="21ed5-123">See Also</span></span>  
 <span data-ttu-id="21ed5-124">[Criar tabelas &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="21ed5-124">[Design Tables &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="21ed5-125">Tópicos de instruções de como criar consultas e exibições &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="21ed5-125">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
