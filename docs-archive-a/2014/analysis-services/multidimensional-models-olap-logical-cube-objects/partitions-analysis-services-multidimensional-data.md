---
title: Partições (Analysis Services-dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- storage [Analysis Services], partitions
- incremental updates [Analysis Services]
- data sources [Analysis Services], partitions
- data storage [Analysis Services]
- aggregations [Analysis Services], partitions
- OLAP objects [Analysis Services], partitions
- storing data [Analysis Services], partitions
- partitions [Analysis Services], about partitions
- cubes [Analysis Services], partitions
- partitions [Analysis Services]
- remote partitions [Analysis Services]
- measure groups [Analysis Services], partitions
ms.assetid: cd10ad00-468c-4d49-9f8d-873494d04b4f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 86057c14655b3fd2f0322387beb16a4a94717b68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583868"
---
# <a name="partitions-analysis-services---multidimensional-data"></a><span data-ttu-id="d68ae-102">Partições (Analysis Services – Dados Multidimensional)</span><span class="sxs-lookup"><span data-stu-id="d68ae-102">Partitions (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="d68ae-103">Uma partição é um contêiner de uma parte dos dados de grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="d68ae-103">A partition is a container for a portion of the measure group data.</span></span> <span data-ttu-id="d68ae-104">As partições não são vistas a partir das consultas MDX; todas as consultas refletem o conteúdo completo do grupo de medidas, independentemente de quantas partições são definidas para o grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="d68ae-104">Partitions are not seen from MDX queries; all queries reflect the whole content of the measure group, regardless of how many partitions are defined for the measure group.</span></span> <span data-ttu-id="d68ae-105">O conteúdo de dados de uma partição é definido pelas associações de consulta da partição e pela divisão da expressão.</span><span class="sxs-lookup"><span data-stu-id="d68ae-105">The data content of a partition is defined by the query bindings of the partition, and by the slicing expression.</span></span>  
  
 <span data-ttu-id="d68ae-106">Um objeto simples <xref:Microsoft.AnalysisServices.Partition> é composto de: informações básicas, definição de divisão, design de agregação e outros.</span><span class="sxs-lookup"><span data-stu-id="d68ae-106">A simple <xref:Microsoft.AnalysisServices.Partition> object is composed of: basic information, slicing definition, aggregation design, and others.</span></span> <span data-ttu-id="d68ae-107">As informações básicas incluem o nome da partição, o modo de armazenamento, o modo de processamento e outros.</span><span class="sxs-lookup"><span data-stu-id="d68ae-107">Basic information includes the name of the partition, the storage mode, the processing mode, and others.</span></span> <span data-ttu-id="d68ae-108">A definição de divisão é uma expressão MDX que especifica uma tupla ou um conjunto.</span><span class="sxs-lookup"><span data-stu-id="d68ae-108">The slicing definition is an MDX expression specifying a tuple or a set.</span></span> <span data-ttu-id="d68ae-109">A definição de divisão tem as mesmas restrições que a função MDX StrToSet.</span><span class="sxs-lookup"><span data-stu-id="d68ae-109">The slicing definition has the same restrictions as the StrToSet MDX function.</span></span> <span data-ttu-id="d68ae-110">Juntamente com o parâmetro CONSTRAINED, a definição de divisão pode usar dimensão, hierarquia, nomes de nível e de membro, chaves, nomes exclusivos e outros objetos nomeados no cubo, mas não pode usar as funções MDX.</span><span class="sxs-lookup"><span data-stu-id="d68ae-110">Together with the CONSTRAINED parameter, the slicing definition can use dimension, hierarchy, level and member names, keys, unique names, or other named objects in the cube, but cannot use MDX functions.</span></span> <span data-ttu-id="d68ae-111">O design de agregação é uma coleção de definições de agregação que podem ser compartilhadas por várias partições.</span><span class="sxs-lookup"><span data-stu-id="d68ae-111">The aggregation design is a collection of aggregation definitions that can be shared across multiple partitions.</span></span> <span data-ttu-id="d68ae-112">O padrão é obtido do design de agregação do cubo pai.</span><span class="sxs-lookup"><span data-stu-id="d68ae-112">The default is taken from the parent cube's aggregation design.</span></span>  
  
 <span data-ttu-id="d68ae-113">As partições são usadas pelo [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para gerenciar e armazenar dados e agregações para um grupo de medidas em um cubo.</span><span class="sxs-lookup"><span data-stu-id="d68ae-113">Partitions are used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to manage and store data and aggregations for a measure group in a cube.</span></span> <span data-ttu-id="d68ae-114">Todo grupo de medidas tem pelo menos uma partição e essa partição é criada quando o grupo de medidas é definido.</span><span class="sxs-lookup"><span data-stu-id="d68ae-114">Every measure group has at least one partition; this partition is created when the measure group is defined.</span></span> <span data-ttu-id="d68ae-115">Ao criar uma nova partição para um grupo de medidas, a nova partição é adicionada ao conjunto de partições que já existem para o grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="d68ae-115">When you create a new partition for a measure group, the new partition is added to the set of partitions that already exist for the measure group.</span></span> <span data-ttu-id="d68ae-116">O grupo de medidas reflete os dados combinados contidos em todas as suas partições.</span><span class="sxs-lookup"><span data-stu-id="d68ae-116">The measure group reflects the combined data that is contained in all its partitions.</span></span> <span data-ttu-id="d68ae-117">Isso significa que você deve assegurar que os dados de uma partição em um grupo de medidas são exclusivos, em relação a qualquer outra partição no grupo de medidas para garantir que os dados não sejam refletidos no grupo de medidas mais de uma vez.</span><span class="sxs-lookup"><span data-stu-id="d68ae-117">This means that you must ensure that the data for a partition in a measure group is exclusive of the data for any other partition in the measure group to ensure that data is not reflected in the measure group more than once.</span></span> <span data-ttu-id="d68ae-118">A partição original do grupo de medidas tem base em uma única tabela de fatos na exibição da fonte de dados do cubo.</span><span class="sxs-lookup"><span data-stu-id="d68ae-118">The original partition for a measure group is based on a single fact table in the data source view of the cube.</span></span> <span data-ttu-id="d68ae-119">Quando há várias partições para o grupo de medidas, cada partição pode fazer referência a uma tabela diferente na exibição da fonte dados ou em uma fonte de dados relacional subjacente do cubo.</span><span class="sxs-lookup"><span data-stu-id="d68ae-119">When there are multiple partitions for a measure group, each partition can reference a different table in either the data source view or in the underlying relational data source for the cube.</span></span> <span data-ttu-id="d68ae-120">Mais de uma partição em um grupo de medidas pode fazer referência à mesma tabela, se cada partição estiver restrita a diferentes linhas na tabela.</span><span class="sxs-lookup"><span data-stu-id="d68ae-120">More than one partition in a measure group can reference the same table, if each partition is restricted to different rows in the table.</span></span>  
  
 <span data-ttu-id="d68ae-121">As partições são poderosas e flexíveis para gerenciar cubos, especialmente cubos grandes.</span><span class="sxs-lookup"><span data-stu-id="d68ae-121">Partitions are a powerful and flexible means of managing cubes, especially large cubes.</span></span> <span data-ttu-id="d68ae-122">Por exemplo, um cubo que contém informações de vendas pode conter uma partição de dados para cada ano passado e também partições para cada trimestre do ano atual.</span><span class="sxs-lookup"><span data-stu-id="d68ae-122">For example, a cube that contains sales information can contain a partition for the data of each past year and also partitions for each quarter of the current year.</span></span> <span data-ttu-id="d68ae-123">Apenas a partição do trimestre atual precisa ser processada quando as informações atuais são adicionadas ao cubo; processar uma quantidade menor de dados aprimorará o desempenho reduzindo o tempo de processamento.</span><span class="sxs-lookup"><span data-stu-id="d68ae-123">Only the current quarter partition needs to be processed when current information is added to the cube; processing a smaller amount of data will improve processing performance by decreasing processing time.</span></span> <span data-ttu-id="d68ae-124">No final do ano, as quatro partições de trimestres podem ser mescladas em uma única partição para cada ano e uma nova partição é criada para o primeiro trimestre do novo ano.</span><span class="sxs-lookup"><span data-stu-id="d68ae-124">At the end of the year the four quarterly partitions can be merged into a single partition for the year and a new partition created for the first quarter of the new year.</span></span> <span data-ttu-id="d68ae-125">Além disso, o processo de criação dessa nova partição pode ser automatizado como parte dos procedimentos de carregamento de data warehouse e processamento do cubo.</span><span class="sxs-lookup"><span data-stu-id="d68ae-125">Further, this new partition creation process can be automated as part of your data warehouse loading and cube processing procedures.</span></span>  
  
 <span data-ttu-id="d68ae-126">As partições não são visíveis para usuários empresariais do cubo.</span><span class="sxs-lookup"><span data-stu-id="d68ae-126">Partitions are not visible to business users of the cube.</span></span> <span data-ttu-id="d68ae-127">Porém, os administradores podem configurar, adicionar ou descartar partições.</span><span class="sxs-lookup"><span data-stu-id="d68ae-127">However, administrators can configure, add, or drop partitions.</span></span> <span data-ttu-id="d68ae-128">Cada partição é armazenada em um conjunto separado de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d68ae-128">Each partition is stored in a separate set of files.</span></span> <span data-ttu-id="d68ae-129">Os dados de agregação de cada partição podem ser armazenados na instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] onde a partição é definida, em outra instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], ou na fonte de dados usada para fornecer os dados de origem da partição.</span><span class="sxs-lookup"><span data-stu-id="d68ae-129">The aggregate data of each partition can be stored on the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] where the partition is defined, on another instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], or in the data source that is used to supply the partition's source data.</span></span> <span data-ttu-id="d68ae-130">As partições permitem que os dados de origem e os dados de agregação do cubo sejam distribuídos por vários discos rígidos e entre diversos computadores.</span><span class="sxs-lookup"><span data-stu-id="d68ae-130">Partitions allow the source data and aggregate data of a cube to be distributed across multiple hard drives and among multiple server computers.</span></span> <span data-ttu-id="d68ae-131">De um cubo moderado a grande, as partições podem aprimorar o desempenho da consulta, desempenho de carregamento e facilitar a manutenção do cubo.</span><span class="sxs-lookup"><span data-stu-id="d68ae-131">For a cube of moderate to large size, partitions can greatly improve query performance, load performance, and ease of cube maintenance.</span></span> <span data-ttu-id="d68ae-132">Para obter mais informações sobre partições remotas, consulte [Partições remotas](partitions-remote-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="d68ae-132">For more information about remote partitions, see [Remote Partitions](partitions-remote-partitions.md).</span></span>  
  
 <span data-ttu-id="d68ae-133">O modo de armazenamento de cada partição pode ser configurado independentemente de outras partições no grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="d68ae-133">The storage mode of each partition can be configured independently of other partitions in the measure group.</span></span> <span data-ttu-id="d68ae-134">As partições podem ser armazenadas, usando qualquer combinação de opções para o local de dados de fonte, modo de armazenamento, cache pró-ativo e projeto de agregação.</span><span class="sxs-lookup"><span data-stu-id="d68ae-134">Partitions can be stored by using any combination of options for source data location, storage mode, proactive caching, and aggregation design.</span></span> <span data-ttu-id="d68ae-135">As opções para OLAP em tempo real e cache pró-ativo permitem equilibrar a velocidade de consulta em relação à latência ao projetar uma partição.</span><span class="sxs-lookup"><span data-stu-id="d68ae-135">Options for real-time OLAP and proactive caching let you balance query speed against latency when you design a partition.</span></span> <span data-ttu-id="d68ae-136">As opções de armazenamento também podem ser aplicadas às dimensões relacionados e aos fatos no grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="d68ae-136">Storage options can also be applied to related dimensions and to facts in a measure group.</span></span> <span data-ttu-id="d68ae-137">Essa flexibilidade permite projetar estratégias de armazenamento de cubo adequadas às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="d68ae-137">This flexibility lets you design cube storage strategies appropriate to your needs.</span></span> <span data-ttu-id="d68ae-138">Para obter mais informações, consulte [modos de armazenamento de partição e processamento](partitions-partition-storage-modes-and-processing.md), [agregações e designs de agregação](aggregations-and-aggregation-designs.md) e [cache pró-ativo &#40;partições&#41;](partitions-proactive-caching.md).</span><span class="sxs-lookup"><span data-stu-id="d68ae-138">For more information, see [Partition Storage Modes and Processing](partitions-partition-storage-modes-and-processing.md), [Aggregations and Aggregation Designs](aggregations-and-aggregation-designs.md) and [Proactive Caching &#40;Partitions&#41;](partitions-proactive-caching.md).</span></span>  
  
## <a name="partition-structure"></a><span data-ttu-id="d68ae-139">Estrutura de partição</span><span class="sxs-lookup"><span data-stu-id="d68ae-139">Partition Structure</span></span>  
 <span data-ttu-id="d68ae-140">A estrutura da partição deve corresponder à estrutura de seu grupo de medidas, o que significa que as medidas, que definem o grupo de medidas, devem ser definidas na partição juntamente com todas as dimensões relacionadas.</span><span class="sxs-lookup"><span data-stu-id="d68ae-140">The structure of a partition must match the structure of its measure group, which means that the measures that define the measure group must also be defined in the partition, along with all related dimensions.</span></span> <span data-ttu-id="d68ae-141">Portanto, quando uma partição é criada, ela herda automaticamente o mesmo conjunto de medidas e dimensões relacionadas definidas para o grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="d68ae-141">Therefore, when a partition is created, it automatically inherits the same set of measures and related dimensions that were defined for the measure group.</span></span>  
  
 <span data-ttu-id="d68ae-142">Entretanto, cada partição em um grupo de medidas pode ter uma tabela de fatos diferente e essas tabelas de fatos podem ser diferentes de suas fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="d68ae-142">However, each partition in a measure group can have a different fact table, and these fact tables can be from different data sources.</span></span> <span data-ttu-id="d68ae-143">Quando partições diferentes em um grupo de medidas têm tabelas de fatos diferentes, as tabelas devem ser suficientemente similares para manter a estrutura do grupo de medidas, o que significa que a consulta de processamento retorna as mesmas colunas e os mesmos tipos de dados de todas as tabelas de fatos para todas as partições.</span><span class="sxs-lookup"><span data-stu-id="d68ae-143">When different partitions in a measure group have different fact tables, the tables must be sufficiently similar to maintain the structure of the measure group, which means that the processing query returns the same columns and same data types for all fact tables for all partitions.</span></span>  
  
 <span data-ttu-id="d68ae-144">Quando tabelas de fatos de diferentes partições forem provenientes de diferentes fontes de dados, as tabelas de fonte de qualquer dimensão relacionada e, também, qualquer tabela de fatos intermediária deve estar presentes em todas as fontes de dados e devem ter a mesma estrutura em todos os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="d68ae-144">When fact tables for different partitions are from different data sources, the source tables for any related dimensions, and also any intermediate fact tables, must also be present in all data sources and must have the same structure in all the databases.</span></span> <span data-ttu-id="d68ae-145">Além disso, todas as colunas de tabelas de dimensões usadas para definir atributos para dimensões do cubo relacionadas ao grupo de medidas devem estar presentes em todas as fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="d68ae-145">Also, all dimension table columns that are used to define attributes for cube dimensions related to the measure group must be present in all of the data sources.</span></span> <span data-ttu-id="d68ae-146">Não há necessidade de definir todas as associações entre a tabela fonte de uma partição e a tabela de dimensões relacionada, se a tabela fonte da partição tiver estrutura idêntica à tabela fonte do grupo de medidas.</span><span class="sxs-lookup"><span data-stu-id="d68ae-146">There is no need to define all the joins between the source table of a partition and a related dimension table if the partition source table has the identical structure as the source table for the measure group.</span></span>  
  
 <span data-ttu-id="d68ae-147">As colunas não usadas para definir medidas no grupo de medidas podem estar presentes em algumas tabelas de fatos, mas ausente em outras.</span><span class="sxs-lookup"><span data-stu-id="d68ae-147">Columns that are not used to define measures in the measure group can be present in some fact tables but absent in others.</span></span> <span data-ttu-id="d68ae-148">Da mesma maneira, as colunas não usadas para definir atributos nas tabelas de dimensões relacionadas podem estar presentes em alguns bancos de dados, mas ausentes em outros.</span><span class="sxs-lookup"><span data-stu-id="d68ae-148">Similarly, columns that are not used to define attributes in related dimension tables can be present in some databases but absent in others.</span></span> <span data-ttu-id="d68ae-149">As tabelas não usadas por tabelas de fatos ou tabelas de dimensões relacionadas podem estar presentes em alguns bancos de dados, mas ausentes em outros.</span><span class="sxs-lookup"><span data-stu-id="d68ae-149">Tables that are not used for either fact tables or related dimension tables can be present in some databases but absent in others.</span></span>  
  
## <a name="data-sources-and-partition-storage"></a><span data-ttu-id="d68ae-150">Fontes de dados e armazenamento de partição</span><span class="sxs-lookup"><span data-stu-id="d68ae-150">Data Sources and Partition Storage</span></span>  
 <span data-ttu-id="d68ae-151">Uma partição tem base em uma tabela, em uma exibição da fonte de dados, em uma tabela ou em uma consulta nomeada na exibição da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="d68ae-151">A partition is based either on a table or view in a data source, or on a table or named query in a data source view.</span></span> <span data-ttu-id="d68ae-152">O local onde os dados de partição são armazenados é definido pela associação da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="d68ae-152">The location where partition data is stored is defined by the data source binding.</span></span> <span data-ttu-id="d68ae-153">Geralmente, você pode particionar um grupo de medidas horizontal ou verticalmente:</span><span class="sxs-lookup"><span data-stu-id="d68ae-153">Typically, you can partition a measure group horizontally or vertically:</span></span>  
  
-   <span data-ttu-id="d68ae-154">Em um grupo de medidas particionado horizontalmente, cada partição em um grupo de medidas tem base em uma tabela separada.</span><span class="sxs-lookup"><span data-stu-id="d68ae-154">In a horizontally partitioned measure group, each partition in a measure group is based on a separate table.</span></span> <span data-ttu-id="d68ae-155">Esse tipo de particionamento é apropriado quando os dados são separados em várias tabelas.</span><span class="sxs-lookup"><span data-stu-id="d68ae-155">This kind of partitioning is appropriate when data is separated into multiple tables.</span></span> <span data-ttu-id="d68ae-156">Por exemplo, alguns bancos de dados relacionais têm uma tabela separada para os dados de cada mês.</span><span class="sxs-lookup"><span data-stu-id="d68ae-156">For example, some relational databases have a separate table for each month's data.</span></span>  
  
-   <span data-ttu-id="d68ae-157">Em um grupo de medidas particionado verticalmente, um grupo de medidas tem base em uma única tabela e cada partição é baseada em uma consulta do sistema fonte que filtra os dados da partição.</span><span class="sxs-lookup"><span data-stu-id="d68ae-157">In a vertically partitioned measure group, a measure group is based on a single table, and each partition is based on a source system query that filters the data for the partition.</span></span> <span data-ttu-id="d68ae-158">Por exemplo, se uma única tabela contiver dados de diversos meses, o grupo de medidas ainda poderá ser particionado por mês aplicando-se uma cláusula WHERE Transact-SQL que retorna os dados do mês separados para cada partição.</span><span class="sxs-lookup"><span data-stu-id="d68ae-158">For example, if a single table contains several months data, the measure group could still be partitioned by month by applying a Transact-SQL WHERE clause that returns a separate month's data for each partition.</span></span>  
  
 <span data-ttu-id="d68ae-159">Cada partição possui configurações de armazenamento que determinam se os dados e agregações para a partição são armazenados no instância local do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou em uma partição remota usando outras instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d68ae-159">Each partition has storage settings that determine whether the data and aggregations for the partition are stored in the local instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] or in a remote partition using another instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="d68ae-160">As configurações de armazenamento podem também especificar o modo de armazenamento e se o cache pró-ativo for usado para controlar a latência de uma partição.</span><span class="sxs-lookup"><span data-stu-id="d68ae-160">The storage settings can also specify the storage mode and whether proactive caching is used to control latency for a partition.</span></span> <span data-ttu-id="d68ae-161">Para obter mais informações, consulte [modos de armazenamento de partição e processamento](partitions-partition-storage-modes-and-processing.md), [cache pró-ativo &#40;partições&#41;](partitions-proactive-caching.md)e [partições remotas](partitions-remote-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="d68ae-161">For more information, see [Partition Storage Modes and Processing](partitions-partition-storage-modes-and-processing.md), [Proactive Caching &#40;Partitions&#41;](partitions-proactive-caching.md), and [Remote Partitions](partitions-remote-partitions.md).</span></span>  
  
## <a name="incremental-updates"></a><span data-ttu-id="d68ae-162">Atualizações incrementais</span><span class="sxs-lookup"><span data-stu-id="d68ae-162">Incremental Updates</span></span>  
 <span data-ttu-id="d68ae-163">Ao criar e gerenciar partições em grupos de medidas de várias partições, você deve tomar precauções especiais para garantir que os dados do cubo sejam precisos.</span><span class="sxs-lookup"><span data-stu-id="d68ae-163">When you create and manage partitions in multiple-partition measure groups, you must take special precautions to guarantee that cube data is accurate.</span></span> <span data-ttu-id="d68ae-164">Apesar dessas precauções não se aplicarem geralmente a grupos de medidas de uma única partição, eles se aplicam quando você atualiza as partições incrementalmente.</span><span class="sxs-lookup"><span data-stu-id="d68ae-164">Although these precautions do not usually apply to single-partition measure groups, they do apply when you incrementally update partitions.</span></span> <span data-ttu-id="d68ae-165">Quando você atualiza uma partição incrementalmente, uma nova partição temporária é criada com a estrutura idêntica à da partição fonte.</span><span class="sxs-lookup"><span data-stu-id="d68ae-165">When you incrementally update a partition, a new temporary partition is created that has a structure identical to that of the source partition.</span></span> <span data-ttu-id="d68ae-166">A partição temporária é processada e então mesclada com a partição fonte.</span><span class="sxs-lookup"><span data-stu-id="d68ae-166">The temporary partition is processed and then merged with the source partition.</span></span> <span data-ttu-id="d68ae-167">Portanto, você deve assegurar que a consulta de processamento que popula a partição temporária não duplique os dados já presentes em uma partição existente.</span><span class="sxs-lookup"><span data-stu-id="d68ae-167">Therefore, you must ensure that the processing query that populates the temporary partition does not duplicate any data already present in an existing partition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d68ae-168">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d68ae-168">See Also</span></span>  
 <span data-ttu-id="d68ae-169">[Configurar propriedades de medida](../multidimensional-models/configure-measure-properties.md) </span><span class="sxs-lookup"><span data-stu-id="d68ae-169">[Configure Measure Properties](../multidimensional-models/configure-measure-properties.md) </span></span>  
 [<span data-ttu-id="d68ae-170">Cubos em modelos multidimensionais</span><span class="sxs-lookup"><span data-stu-id="d68ae-170">Cubes in Multidimensional Models</span></span>](../multidimensional-models/cubes-in-multidimensional-models.md)  
  
  