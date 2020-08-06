---
title: Filtrar dados publicados para replicação de mesclagem | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication [SQL Server replication], filtering published data
- replication [SQL Server], filtering published data
ms.assetid: 46c5023d-7a3b-4455-becc-e159fcb5d6c4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ad9ad45a64f57a6bef8255373180ea943af9893f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568504"
---
# <a name="filter-published-data-for-merge-replication"></a><span data-ttu-id="c205a-102">Filtrar dados publicados para replicação de mesclagem</span><span class="sxs-lookup"><span data-stu-id="c205a-102">Filter Published Data for Merge Replication</span></span>
  <span data-ttu-id="c205a-103">Além dos filtros de linhas estáticas e filtros de colunas que você pode definir com outros tipos de replicação, a replicação de mesclagem oferece filtros de linhas com parâmetros e filtros de junção</span><span class="sxs-lookup"><span data-stu-id="c205a-103">In addition to the static row filters and column filters you can define with other types of replication, merge replication offers parameterized row filters and join filters.</span></span> <span data-ttu-id="c205a-104">Para mais informações sobre filtros de linha estáticos e filtros de coluna, consulte [Filtrar dados publicados](../publish/filter-published-data.md).</span><span class="sxs-lookup"><span data-stu-id="c205a-104">For more information about static row filters and column filters, see [Filter Published Data](../publish/filter-published-data.md).</span></span>  
  
 <span data-ttu-id="c205a-105">A replicação de mesclagem é usada em muitos aplicativos para oferecer suporte a usuários móveis, esses aplicativos costumam ter um grande número de assinaturas com cada assinatura, recebendo um conjunto de dados exclusivo.</span><span class="sxs-lookup"><span data-stu-id="c205a-105">Merge replication is used in many applications that support mobile users; these applications usually have a large number of subscriptions with each subscription receiving a unique data set.</span></span> <span data-ttu-id="c205a-106">Filtros com parâmetros, combinados com filtros de junção, permitem que um administrador defina uma publicação (ou no máximo um pequeno número de publicações) e forneça diferentes conjuntos de dados para usuários, reduzindo o gerenciamento de sobrecarga introduzido pela criação de múltiplas publicações.</span><span class="sxs-lookup"><span data-stu-id="c205a-106">Parameterized filters combined with join filters allow an administrator to set up one publication (or at most a small number of publications) and yet provide different data sets to users, reducing the management overhead introduced by creating multiple publications.</span></span>  
  
-   <span data-ttu-id="c205a-107">Os filtros com parâmetros permitem que diferentes partições de dados sejam enviados à diferentes Assinaturas sem a necessidade de que sejam criadas múltiplas publicações.</span><span class="sxs-lookup"><span data-stu-id="c205a-107">Parameterized filters allow different partitions of data to be sent to different Subscribers without requiring multiple publications to be created.</span></span> <span data-ttu-id="c205a-108">Por exemplo, uma tabela pode ser filtrada para que os dados de um determinado representante de vendas seja replicado apenas para aquele representante.</span><span class="sxs-lookup"><span data-stu-id="c205a-108">For example, a table can be filtered so that data for a given sales representative is replicated only to that representative.</span></span> <span data-ttu-id="c205a-109">Os filtros com parâmetros têm uma variedade de opções que permitem o ajuste da filtragem para otimizar o desempenho e melhor correspondência aos dados e requisitos do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c205a-109">Parameterized filters have a variety of options that allow you to tailor filtering to optimize performance and best match your data and application requirements.</span></span> <span data-ttu-id="c205a-110">Para obter mais informações, consulte [Filtros de linha com parâmetros](parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="c205a-110">For more information, see [Parameterized Row Filters](parameterized-filters-parameterized-row-filters.md).</span></span>  
  
-   <span data-ttu-id="c205a-111">Os filtros de junção são usados normalmente em conjunto com filtros com parâmetros para estender a filtragem às tabelas relacionadas (também podem ser usados em conjunto com os filtros estáticos).</span><span class="sxs-lookup"><span data-stu-id="c205a-111">Join filters are typically used in conjunction with parameterized filters to extend filtering to related tables (they can also be used in conjunction with static filters).</span></span> <span data-ttu-id="c205a-112">Por exemplo, o representante de vendas geralmente tem dados em outras tabelas como as tabelas de clientes e pedidos.</span><span class="sxs-lookup"><span data-stu-id="c205a-112">For example, the sales representative typically has data in other tables such as customer and order tables.</span></span> <span data-ttu-id="c205a-113">Esses dados podem ser filtrados para que o representante de vendas recebe apenas os dados sobre seus clientes e pedidos de seus clientes.</span><span class="sxs-lookup"><span data-stu-id="c205a-113">This data can be filtered so the sales representative receives only the data on her customers and her customers' orders.</span></span> <span data-ttu-id="c205a-114">Para obter mais informações, consulte [Join Filters](join-filters.md).</span><span class="sxs-lookup"><span data-stu-id="c205a-114">For more information, see [Join Filters](join-filters.md).</span></span>  
  
 <span data-ttu-id="c205a-115">Um filtro não deve incluir o `rowguidcol` usado por replicação para identificar linhas.</span><span class="sxs-lookup"><span data-stu-id="c205a-115">A filter must not include the `rowguidcol` used by replication to identify rows.</span></span> <span data-ttu-id="c205a-116">Por padrão, esta é a coluna adicionada no momento que você define a replicação de mesclagem e é denominada **rowguid**.</span><span class="sxs-lookup"><span data-stu-id="c205a-116">By default this is the column added at the time you set up merge replication and is named **rowguid**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c205a-117">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c205a-117">See Also</span></span>  
 [<span data-ttu-id="c205a-118">Publicar dados e objetos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="c205a-118">Publish Data and Database Objects</span></span>](../publish/publish-data-and-database-objects.md)  
  
  
