---
title: Opções de esquema de banco de dados da área de assunto (Assistente de geração de esquema) (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.schemagenwizard.subjectareaschemaopts.f1
ms.assetid: 4c109bb8-e19d-412b-908f-bfdd7f872439
author: minewiskan
ms.author: owend
ms.openlocfilehash: 98460332478d02de823addcd113fb9c1e87d6958
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572720"
---
# <a name="subject-area-database-schema-options-schema-generation-wizard-analysis-services---multidimensional-data"></a><span data-ttu-id="0a15f-102">Opções de Esquema de Banco de Dados da Área de Assunto (Assistente de Geração de Esquema) (Analysis Services - Dados Multidimensionais)</span><span class="sxs-lookup"><span data-stu-id="0a15f-102">Subject Area Database Schema Options (Schema Generation Wizard) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="0a15f-103">Use a página **Opções de Esquema de Banco de Dados da Área de Assunto** para controlar como o esquema é gerado, bem como para definir como os dados são preservados.</span><span class="sxs-lookup"><span data-stu-id="0a15f-103">Use the **Subject Area Database Schema Options** page to control how the schema is generated, as well as to define how data is preserved.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0a15f-104">Opções</span><span class="sxs-lookup"><span data-stu-id="0a15f-104">Options</span></span>  
 <span data-ttu-id="0a15f-105">**Esquema de Propriedade**</span><span class="sxs-lookup"><span data-stu-id="0a15f-105">**Owning schema**</span></span>  
 <span data-ttu-id="0a15f-106">Especifica o nome do esquema dentro do banco de dados da nova área de assunto.</span><span class="sxs-lookup"><span data-stu-id="0a15f-106">Specifies the name of the schema within the new subject area database.</span></span>  
  
 <span data-ttu-id="0a15f-107">**Criar chaves primárias em tabelas de dimensões**</span><span class="sxs-lookup"><span data-stu-id="0a15f-107">**Create primary keys on dimension tables**</span></span>  
 <span data-ttu-id="0a15f-108">Cria chaves primárias nas tabelas de dimensões no esquema gerado.</span><span class="sxs-lookup"><span data-stu-id="0a15f-108">Creates primary keys on the dimension tables in the generated schema.</span></span> <span data-ttu-id="0a15f-109">Nenhum índice será gerado se você não selecionar esta opção.</span><span class="sxs-lookup"><span data-stu-id="0a15f-109">No index is generated if you do not select this option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a15f-110">Se você não selecionar esta opção, a integridade referencial será imposta.</span><span class="sxs-lookup"><span data-stu-id="0a15f-110">If you do not select this option, referential integrity is enforced.</span></span>  
  
 <span data-ttu-id="0a15f-111">**Criar índices**</span><span class="sxs-lookup"><span data-stu-id="0a15f-111">**Create indexes**</span></span>  
 <span data-ttu-id="0a15f-112">Cria índices em colunas de chave estrangeira no esquema gerado.</span><span class="sxs-lookup"><span data-stu-id="0a15f-112">Creates indexes on foreign key columns in the generated schema.</span></span>  
  
 <span data-ttu-id="0a15f-113">**Impor a integridade referencial**</span><span class="sxs-lookup"><span data-stu-id="0a15f-113">**Enforce referential integrity**</span></span>  
 <span data-ttu-id="0a15f-114">Impõe a integridade referencial dentro do esquema gerado.</span><span class="sxs-lookup"><span data-stu-id="0a15f-114">Enforces referential integrity within the generated schema.</span></span> <span data-ttu-id="0a15f-115">Se você não selecionar esta opção, relações serão criadas, mas não impostas.</span><span class="sxs-lookup"><span data-stu-id="0a15f-115">If you do not select this option, relationships are created but not enforced.</span></span>  
  
 <span data-ttu-id="0a15f-116">**Preservar os dados na regeneração**</span><span class="sxs-lookup"><span data-stu-id="0a15f-116">**Preserve data on regeneration**</span></span>  
 <span data-ttu-id="0a15f-117">Retém dados no banco de dados de área de assunto quando o assistente é concluído.</span><span class="sxs-lookup"><span data-stu-id="0a15f-117">Retains data in the subject area database when the wizard finishes.</span></span> <span data-ttu-id="0a15f-118">Se esta opção não for selecionada, todos os dados do banco de dados da área de assunto poderão ser apagados sem aviso prévio.</span><span class="sxs-lookup"><span data-stu-id="0a15f-118">If you do not select this option, all the data in the subject area database may be erased without warning.</span></span>  
  
 <span data-ttu-id="0a15f-119">**Popular tabela(s) de tempo**</span><span class="sxs-lookup"><span data-stu-id="0a15f-119">**Populate time table(s)**</span></span>  
 <span data-ttu-id="0a15f-120">Especifica como o assistente popula as tabelas de tempo.</span><span class="sxs-lookup"><span data-stu-id="0a15f-120">Specifies how the wizard populates the time tables.</span></span> <span data-ttu-id="0a15f-121">A tabela a seguir descreve os possíveis valores para esta opção.</span><span class="sxs-lookup"><span data-stu-id="0a15f-121">The following table describes the possible values for this option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a15f-122">Essa opção será habilitada apenas se o Assistente de Geração de Esquema for chamado no projeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] usando o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] no modo de projeto.</span><span class="sxs-lookup"><span data-stu-id="0a15f-122">This option is enabled only if Schema Generation Wizard is called from an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, using [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] in project mode.</span></span>  
  
|<span data-ttu-id="0a15f-123">Valor</span><span class="sxs-lookup"><span data-stu-id="0a15f-123">Value</span></span>|<span data-ttu-id="0a15f-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="0a15f-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0a15f-125">Popular</span><span class="sxs-lookup"><span data-stu-id="0a15f-125">Populate</span></span>|<span data-ttu-id="0a15f-126">As tabelas de tempo de área de assunto são populadas.</span><span class="sxs-lookup"><span data-stu-id="0a15f-126">The subject area time tables are populated.</span></span>|  
|<span data-ttu-id="0a15f-127">Não popular</span><span class="sxs-lookup"><span data-stu-id="0a15f-127">Do not populate</span></span>|<span data-ttu-id="0a15f-128">As tabelas de tempo de área de assunto não são populadas.</span><span class="sxs-lookup"><span data-stu-id="0a15f-128">The subject area time tables are not populated.</span></span>|  
|<span data-ttu-id="0a15f-129">Popular somente se estiver vazia</span><span class="sxs-lookup"><span data-stu-id="0a15f-129">Populate only if empty</span></span>|<span data-ttu-id="0a15f-130">As tabelas de tempo de área de assunto serão populadas apenas se estiverem vazias.</span><span class="sxs-lookup"><span data-stu-id="0a15f-130">The subject area time tables are populated only if they are empty.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0a15f-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0a15f-131">See Also</span></span>  
 [<span data-ttu-id="0a15f-132">Ajuda F1 do assistente de geração de esquema &#40;Analysis Services dados multidimensionais&#41;</span><span class="sxs-lookup"><span data-stu-id="0a15f-132">Schema Generation Wizard F1 Help &#40;Analysis Services - Multidimensional Data&#41;</span></span>](schema-generation-wizard-f1-help-analysis-services-multidimensional-data.md)  
  
  
