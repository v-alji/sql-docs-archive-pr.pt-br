---
title: Gerenciar alterações em exibições de fonte de dados e fontes de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying data sources
- modifying data source views
- data source views [Analysis Services], schema updates
- data sources [Analysis Services], schema updates
ms.assetid: 928c9f63-365a-43fd-9bbd-78828cc7e54d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0f558ce6aaf9e57576d5773322352d33b81a3392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680100"
---
# <a name="manage-changes-to-data-source-views-and-data-sources"></a><span data-ttu-id="3a24f-102">Gerenciar alterações em exibições da fonte de dados e em fontes de dados</span><span class="sxs-lookup"><span data-stu-id="3a24f-102">Manage Changes to Data Source Views and Data Sources</span></span>
  <span data-ttu-id="3a24f-103">Quando o Assistente de Geração de Esquema é executado novamente, ele reutiliza a fonte de dados e a exibição da fonte de dados usadas na geração original.</span><span class="sxs-lookup"><span data-stu-id="3a24f-103">When the Schema Generation Wizard is rerun, it reuses the same data source and data source view that it used for the original generation.</span></span> <span data-ttu-id="3a24f-104">Se você adicionar uma fonte de dados ou uma exibição da fonte de dados, o assistente não a usará.</span><span class="sxs-lookup"><span data-stu-id="3a24f-104">If you add a data source or a data source view, the wizard does not use it.</span></span> <span data-ttu-id="3a24f-105">Se você excluir a fonte de dados ou a exibição da fonte de dados original depois da geração inicial, execute o assistente desde o início.</span><span class="sxs-lookup"><span data-stu-id="3a24f-105">If you delete the original data source or data source view after the initial generation, you must run the wizard from the beginning.</span></span> <span data-ttu-id="3a24f-106">Também são excluídas todas as configurações anteriores do assistente.</span><span class="sxs-lookup"><span data-stu-id="3a24f-106">All previous settings in the wizard are also deleted.</span></span> <span data-ttu-id="3a24f-107">Todos os objetos existentes em um banco de dados subjacente que estavam vinculados a uma fonte de dados ou exibição de fonte de dados excluída serão tratados como objetos criados pelo usuário na próxima vez que você executar o Assistente de Geração de Esquema.</span><span class="sxs-lookup"><span data-stu-id="3a24f-107">Any existing objects in an underlying database that were bound to a deleted data source or data source view are treated as user-created objects the next time you run the Schema Generation Wizard.</span></span>  
  
 <span data-ttu-id="3a24f-108">Se a exibição da fonte de dados não refletir o estado real do banco de dados subjacente no momento da geração, o Assistente de Geração de Esquema pode encontrar erros ao gerar o esquema para o banco de dados da área de assunto.</span><span class="sxs-lookup"><span data-stu-id="3a24f-108">If the data source view does not reflect the actual state of the underlying database at the time of generation, the Schema Generation Wizard may encounter errors when it generates the schema for the subject area database.</span></span> <span data-ttu-id="3a24f-109">Por exemplo, se a exibição da fonte de dados especificar que o tipo de dados de uma coluna é **int**, mas, na verdade, o tipo de dados da coluna for **string**, o Assistente de Geração de Esquema definirá o tipo de dados da chave estrangeira como **INT** de acordo com a exibição da fonte de dados e, em seguida, não conseguirá criar a relação, pois o tipo de dados real é **string**.</span><span class="sxs-lookup"><span data-stu-id="3a24f-109">For example, if the data source view specifies that the data type for a column is **int**, but data type for the column is actually **string**, the Schema Generation Wizard sets the data type for the foreign key to **INT** to match the data source view and then fails when it creates the relationship because the actual type is **string**.</span></span>  
  
 <span data-ttu-id="3a24f-110">Por outro lado, se você alterar a cadeia de conexão da fonte de dados para um banco de dados diferente daquele usado na geração anterior, nenhum erro será gerado.</span><span class="sxs-lookup"><span data-stu-id="3a24f-110">On the other hand, if you change the data source connection string to a different database from the previous generation, no error is generated.</span></span> <span data-ttu-id="3a24f-111">O novo banco de dados será usado e nenhuma alteração será feita no banco de dados anterior.</span><span class="sxs-lookup"><span data-stu-id="3a24f-111">The new database is used, and no change is made to the previous database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a24f-112">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3a24f-112">See Also</span></span>  
 [<span data-ttu-id="3a24f-113">Entendendo a geração com incremento</span><span class="sxs-lookup"><span data-stu-id="3a24f-113">Understanding Incremental Generation</span></span>](understanding-incremental-generation.md)  
  
  
