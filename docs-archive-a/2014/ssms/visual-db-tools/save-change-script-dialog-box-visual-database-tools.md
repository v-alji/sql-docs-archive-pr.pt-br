---
title: Caixa de diálogo Salvar Script de Alteração (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.generatechangescript
- vdtsql.chm:65544
ms.assetid: fc9d1639-5efa-44fe-a04f-4d4d0def2833
author: stevestein
ms.author: sstein
ms.openlocfilehash: 19a2bb2ce9a219c195421e2efa203fc115e1ae1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678478"
---
# <a name="save-change-script-dialog-box-visual-database-tools"></a><span data-ttu-id="ca156-102">Caixa de diálogo Salvar Script de Alteração (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="ca156-102">Save Change Script Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="ca156-103">Essa caixa de diálogo mostra o script do [!INCLUDE[tsql](../../includes/tsql-md.md)] para as alterações que você fez desde a última vez em que você salvou a tabela.</span><span class="sxs-lookup"><span data-stu-id="ca156-103">This dialog box shows the [!INCLUDE[tsql](../../includes/tsql-md.md)] script for the changes you have made since you last saved the table.</span></span> <span data-ttu-id="ca156-104">Isso também lhe permite salvar o script para um arquivo de texto em um local de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="ca156-104">It also allows you to save the script to a text file at a location you choose.</span></span>  
  
 <span data-ttu-id="ca156-105">Você pode acessar essa caixa de diálogo depois de ter feito alterações não salvas em uma tabela no Designer de tabela.</span><span class="sxs-lookup"><span data-stu-id="ca156-105">You can access this dialog box after you have made unsaved changes to a table in Table Designer.</span></span> <span data-ttu-id="ca156-106">No menu **Designer de Tabela** , clique em **Gerar Script de Alteração**.</span><span class="sxs-lookup"><span data-stu-id="ca156-106">On the **Table Designer** menu, click **Generate Change Script**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ca156-107">Scripts de alteração fornecidos pelo Visual Database Tools não contêm nenhum tratamento de erros.</span><span class="sxs-lookup"><span data-stu-id="ca156-107">Change scripts provided by Visual Database Tools contain no error handling.</span></span> <span data-ttu-id="ca156-108">Eles assumem que os objetos de banco de dados não foram alterados desde que a ferramenta foi aberta e que, portanto, não ocorrerão problemas relacionados a alterações.</span><span class="sxs-lookup"><span data-stu-id="ca156-108">They assume that database objects have not changed since the tool was opened, and that change-related problems will therefore not occur.</span></span> <span data-ttu-id="ca156-109">Antes de executar um script de alteração, deve-se incluir as instruções adequadas de tratamento de erros.</span><span class="sxs-lookup"><span data-stu-id="ca156-109">Before running a change script, you should include the appropriate error-handling statements.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ca156-110">Opções</span><span class="sxs-lookup"><span data-stu-id="ca156-110">Options</span></span>  
 <span data-ttu-id="ca156-111">**Gerar script de alteração automaticamente em todos os salvamentos**</span><span class="sxs-lookup"><span data-stu-id="ca156-111">**Automatically generate change script on every save**</span></span>  
 <span data-ttu-id="ca156-112">Se a caixa de diálogo **Salvar Script de Alteração** estiver marcada, ela aparecerá sempre que você salvar alterações em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="ca156-112">If checked, the **Save Change Script** dialog box will appear any time you save changes to a table.</span></span>  
  
 <span data-ttu-id="ca156-113">**Sim**</span><span class="sxs-lookup"><span data-stu-id="ca156-113">**Yes**</span></span>  
 <span data-ttu-id="ca156-114">Ative a caixa de diálogo **Salvar** , em que você poderá escolher o local para o arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="ca156-114">Bring up the **Save** dialog box where you can choose the location for the text file.</span></span>  
  
 <span data-ttu-id="ca156-115">**Não**</span><span class="sxs-lookup"><span data-stu-id="ca156-115">**No**</span></span>  
 <span data-ttu-id="ca156-116">Cancele a criação do script de alteração.</span><span class="sxs-lookup"><span data-stu-id="ca156-116">Cancel the creation of the change script.</span></span>  
  
  
