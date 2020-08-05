---
title: Validando dados (Suplemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 71eda98f-01a4-4fff-8246-be3133782523
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f8e97ff6481996b2e16436e1f78478bd234fe6ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574083"
---
# <a name="validating-data-mds-add-in-for-excel"></a><span data-ttu-id="c32db-102">Validando dados (Suplemento do MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="c32db-102">Validating Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="c32db-103">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], quando você publica dados, ocorrem dois tipos de validação:</span><span class="sxs-lookup"><span data-stu-id="c32db-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], when you publish data, two types of validation take place:</span></span>  
  
-   <span data-ttu-id="c32db-104">Qualquer regra de negócio definida é aplicada aos dados.</span><span class="sxs-lookup"><span data-stu-id="c32db-104">Any defined business rules are applied to the data.</span></span>  
  
-   <span data-ttu-id="c32db-105">Os dados são verificados quanto a valores de atributo permitidos (por exemplo, número de caracteres ou tipo de dados).</span><span class="sxs-lookup"><span data-stu-id="c32db-105">Data is checked against allowed attribute values (for example, number of characters or type of data).</span></span>  
  
 <span data-ttu-id="c32db-106">Em cada caso, os dados válidos são publicados no repositório do MDS.</span><span class="sxs-lookup"><span data-stu-id="c32db-106">In each case, valid data is published to the MDS repository.</span></span> <span data-ttu-id="c32db-107">Os dados que não são válidos são realçados e detalhes do erro podem ser mostrados em colunas de status.</span><span class="sxs-lookup"><span data-stu-id="c32db-107">Data that is not valid is highlighted, and details of the error can be shown in status columns.</span></span>  
  
## <a name="when-validation-occurs"></a><span data-ttu-id="c32db-108">Quando ocorre a validação</span><span class="sxs-lookup"><span data-stu-id="c32db-108">When Validation Occurs</span></span>  
 <span data-ttu-id="c32db-109">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], a validação ocorre quando você publica novos dados ou altera os existentes ou quando aplica regras de negócio manualmente.</span><span class="sxs-lookup"><span data-stu-id="c32db-109">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], validation occurs when you publish new or changed data, or when you manually apply business rules.</span></span>  
  
 <span data-ttu-id="c32db-110">Quando as regras de negócio falham, os dados ainda são publicados no repositório do MDS.</span><span class="sxs-lookup"><span data-stu-id="c32db-110">When business rules fail, the data is still published to the MDS repository.</span></span> <span data-ttu-id="c32db-111">Quando a validação de entrada falha, os dados não são publicados no repositório.</span><span class="sxs-lookup"><span data-stu-id="c32db-111">When input validation fails, the data is not published to the repository.</span></span>  
  
## <a name="validation-statuses"></a><span data-ttu-id="c32db-112">Status da validação</span><span class="sxs-lookup"><span data-stu-id="c32db-112">Validation Statuses</span></span>  
 <span data-ttu-id="c32db-113">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], os status de validação a seguir são possíveis.</span><span class="sxs-lookup"><span data-stu-id="c32db-113">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], the following validation statuses are possible.</span></span>  
  
|<span data-ttu-id="c32db-114">Status</span><span class="sxs-lookup"><span data-stu-id="c32db-114">Status</span></span>|<span data-ttu-id="c32db-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="c32db-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c32db-116">Erro</span><span class="sxs-lookup"><span data-stu-id="c32db-116">Error</span></span>|<span data-ttu-id="c32db-117">Um ou mais valores na linha validação falharam na validação em relação a regras de negócio definidas por um administrador do MDS.</span><span class="sxs-lookup"><span data-stu-id="c32db-117">One or more values in the row failed validation against business rules defined by an MDS administrator.</span></span>|  
|<span data-ttu-id="c32db-118">Não Validado</span><span class="sxs-lookup"><span data-stu-id="c32db-118">Not Validated</span></span>|<span data-ttu-id="c32db-119">Os valores na linha ainda não foram validados em relação a regras de negócio.</span><span class="sxs-lookup"><span data-stu-id="c32db-119">Values in the row have not yet been validated against business rules.</span></span>|  
|<span data-ttu-id="c32db-120">Sucesso</span><span class="sxs-lookup"><span data-stu-id="c32db-120">Success</span></span>|<span data-ttu-id="c32db-121">Todos os valores na linha passaram na validação quanto a regras de negócio.</span><span class="sxs-lookup"><span data-stu-id="c32db-121">All values in the row have passed validation against business rules.</span></span>|  
  
## <a name="input-statuses"></a><span data-ttu-id="c32db-122">Status de Entrada</span><span class="sxs-lookup"><span data-stu-id="c32db-122">Input Statuses</span></span>  
 <span data-ttu-id="c32db-123">No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], os status de entrada a seguir são possíveis</span><span class="sxs-lookup"><span data-stu-id="c32db-123">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], the following input statuses are possible</span></span>  
  
|<span data-ttu-id="c32db-124">Status</span><span class="sxs-lookup"><span data-stu-id="c32db-124">Status</span></span>|<span data-ttu-id="c32db-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="c32db-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c32db-126">Erro</span><span class="sxs-lookup"><span data-stu-id="c32db-126">Error</span></span>|<span data-ttu-id="c32db-127">Um ou mais valores na linha não atendem aos requisitos de sistema, como comprimento ou tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="c32db-127">One or more values in the row don't meet system requirements like length or data type.</span></span> <span data-ttu-id="c32db-128">O valor não é atualizado no repositório do MDS.</span><span class="sxs-lookup"><span data-stu-id="c32db-128">The value is not updated in the MDS repository.</span></span>|  
|<span data-ttu-id="c32db-129">Nova Linha</span><span class="sxs-lookup"><span data-stu-id="c32db-129">New Row</span></span>|<span data-ttu-id="c32db-130">Os valores na linha ainda não foram publicados no repositório do MDS.</span><span class="sxs-lookup"><span data-stu-id="c32db-130">The values in the row have not yet been published to the MDS repository.</span></span>|  
|<span data-ttu-id="c32db-131">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="c32db-131">Read Only</span></span>|<span data-ttu-id="c32db-132">O usuário registrado em log tem permissões Somente leitura para um ou mais valores na linha e os valores não podem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="c32db-132">The logged in user has Read-only permissions to one or more values in the row and the value(s) cannot be updated.</span></span>|  
|<span data-ttu-id="c32db-133">Inalterado</span><span class="sxs-lookup"><span data-stu-id="c32db-133">Unchanged</span></span>|<span data-ttu-id="c32db-134">Nenhum valor na linha foi alterado na planilha.</span><span class="sxs-lookup"><span data-stu-id="c32db-134">No values in the row have been changed in the worksheet.</span></span> <span data-ttu-id="c32db-135">Isso não significa que os valores no repositório não foram alterados; para obter os dados mais recentes na planilha, no grupo **Conectar e Carregar** , clique em **Carregar ou Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="c32db-135">This does not mean the values in the repository have not changed; to get the latest data in the sheet, in the **Connect and Load** group, click **Load or Refresh**.</span></span><br /><br /> <span data-ttu-id="c32db-136">Essa é a configuração padrão para cada linha.</span><span class="sxs-lookup"><span data-stu-id="c32db-136">This is the default setting for each row.</span></span>|  
  
## <a name="related-tasks"></a><span data-ttu-id="c32db-137">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="c32db-137">Related Tasks</span></span>  
  
|<span data-ttu-id="c32db-138">Descrição da tarefa</span><span class="sxs-lookup"><span data-stu-id="c32db-138">Task Description</span></span>|<span data-ttu-id="c32db-139">Tópico</span><span class="sxs-lookup"><span data-stu-id="c32db-139">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="c32db-140">Determine quais valores não transmitem as regras de negócio definidas.</span><span class="sxs-lookup"><span data-stu-id="c32db-140">Determine which values do not pass the defined business rules.</span></span>|[<span data-ttu-id="c32db-141">Aplicar regras de negócio &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="c32db-141">Apply Business Rules &#40;MDS Add-in for Excel&#41;</span></span>](apply-business-rules-mds-add-in-for-excel.md)|  
|<span data-ttu-id="c32db-142">Para ajudar a corrigir erros de validação, exiba todas as transações que ocorreram para um membro.</span><span class="sxs-lookup"><span data-stu-id="c32db-142">To help correct validation errors, view all transactions that have taken place for a member.</span></span>|[<span data-ttu-id="c32db-143">Exibir todas as anotações ou transações de um membro &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="c32db-143">View All Annotations or Transactions for a Member &#40;MDS Add-in for Excel&#41;</span></span>](view-all-annotations-or-transactions-for-a-member-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="c32db-144">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="c32db-144">Related Content</span></span>  
  
-   [<span data-ttu-id="c32db-145">Publicando dados &#40;Suplemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="c32db-145">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
  
