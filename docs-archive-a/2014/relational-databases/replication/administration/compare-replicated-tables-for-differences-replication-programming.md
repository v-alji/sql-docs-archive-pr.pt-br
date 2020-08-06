---
title: Comparar tabelas replicadas para descobrir diferenças (Programação de replicação) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- tablediff utility
- comparing replicated tables
ms.assetid: cd253a17-0c85-42b4-912c-690169ebe799
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0d804c7d4ac9cc54fa144b7054c6032663b76c0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685597"
---
# <a name="compare-replicated-tables-for-differences-replication-programming"></a><span data-ttu-id="b457d-102">Comparar tabelas replicadas para descobrir diferenças (Programação de replicação)</span><span class="sxs-lookup"><span data-stu-id="b457d-102">Compare Replicated Tables for Differences (Replication Programming)</span></span>
  <span data-ttu-id="b457d-103">A validação de artigo é usada para determinar se os dados publicados em artigos de tabelas no Publicador e no Assinante não são idênticos, pois isso poderia indicar não convergência.</span><span class="sxs-lookup"><span data-stu-id="b457d-103">Article validation is used to determine if published data for table articles at the Publisher and Subscriber are not identical, which can indicate non-convergence.</span></span> <span data-ttu-id="b457d-104">Para obter mais informações, consulte [Validar os dados replicados](../validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="b457d-104">For more information, see [Validate Replicated Data](../validate-data-at-the-subscriber.md).</span></span> <span data-ttu-id="b457d-105">Entretanto, a validação apenas retorna informações que passaram ou falharam e não fornece informação sobre qual é a diferença entre as tabelas de origem e de destino.</span><span class="sxs-lookup"><span data-stu-id="b457d-105">However, validation only returns pass or fail information and does not provide any information about what is different between the source and destination tables.</span></span> <span data-ttu-id="b457d-106">O utilitário de prompt de comando **tablediff** retorna informações detalhadas sobre a diferença entre duas tabelas e pode até gerar um script [!INCLUDE[tsql](../../../includes/tsql-md.md)] para fazer convergir a assinatura com os dados no Publicador.</span><span class="sxs-lookup"><span data-stu-id="b457d-106">The **tablediff** command prompt utility returns detailed difference information between two tables and can even generate a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script to bring a subscription into convergence with data at the Publisher.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b457d-107">O utilitário **tablediff** tem suporte apenas nos servidores [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b457d-107">The **tablediff** utility is only supported for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] servers.</span></span>  
  
### <a name="to-compare-replicated-tables-for-differences-using-tablediff"></a><span data-ttu-id="b457d-108">Para comparar tabelas replicadas e encontrar diferenças usando tablediff</span><span class="sxs-lookup"><span data-stu-id="b457d-108">To compare replicated tables for differences using tablediff</span></span>  
  
1.  <span data-ttu-id="b457d-109">No prompt de comando de qualquer servidor em uma topologia de replicação, execute o [tablediff Utility](../../../tools/tablediff-utility.md).</span><span class="sxs-lookup"><span data-stu-id="b457d-109">From the command prompt at any server in a replication topology, run the [tablediff Utility](../../../tools/tablediff-utility.md).</span></span> <span data-ttu-id="b457d-110">Especifique os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="b457d-110">Specify the following parameters:</span></span>  
  
    -   <span data-ttu-id="b457d-111">**- sourceserver** - nome do servidor no qual os dados são os corretos, normalmente o Publicador.</span><span class="sxs-lookup"><span data-stu-id="b457d-111">**-sourceserver** - name of the server on which the data is known to be correct, usually the Publisher.</span></span>  
  
    -   <span data-ttu-id="b457d-112">**- sourcedatabase** - nome do banco de dados que contém os dados corretos.</span><span class="sxs-lookup"><span data-stu-id="b457d-112">**-sourcedatabase** - name of the database containing the correct data.</span></span>  
  
    -   <span data-ttu-id="b457d-113">**- sourcetable** - nome da tabela de origem do artigo que é comparado.</span><span class="sxs-lookup"><span data-stu-id="b457d-113">**-sourcetable** - name of the source table for the article being compared.</span></span>  
  
    -   <span data-ttu-id="b457d-114">(Opcional) **- sourceschema** - proprietário do esquema da tabela de origem, se não for o esquema padrão.</span><span class="sxs-lookup"><span data-stu-id="b457d-114">(Optional) **-sourceschema** - schema owner of the source table, if not the default schema.</span></span>  
  
    -   <span data-ttu-id="b457d-115">(Opcional) **-sourceuser** e **-sourcepassword** quando usar a Autenticação do SQL Server para se conectar ao Publicador.</span><span class="sxs-lookup"><span data-stu-id="b457d-115">(Optional) **-sourceuser** and **-sourcepassword** when using SQL Server Authentication to connect to the Publisher.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="b457d-116">Quando possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="b457d-116">When possible, use Windows Authentication.</span></span> <span data-ttu-id="b457d-117">Se você precisa usar Autenticação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , solicite aos usuários para entrar com credenciais de segurança em runtime.</span><span class="sxs-lookup"><span data-stu-id="b457d-117">If you must use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="b457d-118">Se for necessário armazenar credenciais em um arquivo de script, você deverá proteger o arquivo para impedir acesso não autorizado.</span><span class="sxs-lookup"><span data-stu-id="b457d-118">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
    -   <span data-ttu-id="b457d-119">**- destinationserver** - nome do servidor no qual os dados estão sendo comparados, normalmente um Assinante.</span><span class="sxs-lookup"><span data-stu-id="b457d-119">**-destinationserver** - name of the server on which the data is being compared, usually a Subscriber.</span></span>  
  
    -   <span data-ttu-id="b457d-120">**- destinationdatabase** - nome do banco de dados que é comparado.</span><span class="sxs-lookup"><span data-stu-id="b457d-120">**-destinationdatabase** - name of a the database being compared.</span></span>  
  
    -   <span data-ttu-id="b457d-121">**- destinationtable** - nome da tabela que é comparada.</span><span class="sxs-lookup"><span data-stu-id="b457d-121">**-destinationtable** - name of the table being compared.</span></span>  
  
    -   <span data-ttu-id="b457d-122">(Opcional) **- destinationschema** - proprietário do esquema da tabela de destino, se não for o esquema padrão.</span><span class="sxs-lookup"><span data-stu-id="b457d-122">(Optional) **-destinationschema** - schema owner of the destination table, if not the default schema.</span></span>  
  
    -   <span data-ttu-id="b457d-123">(Opcional) **- destinationuser** e **- destinationpassword** ao usar Autenticação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para conectar ao Assinante.</span><span class="sxs-lookup"><span data-stu-id="b457d-123">(Optional) **-destinationuser** and **-destinationpassword** when using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication to connect to the Subscriber.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="b457d-124">Quando possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="b457d-124">When possible, use Windows Authentication.</span></span> <span data-ttu-id="b457d-125">Se você precisa usar Autenticação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , solicite aos usuários para entrar com credenciais de segurança em runtime.</span><span class="sxs-lookup"><span data-stu-id="b457d-125">If you must use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="b457d-126">Se for necessário armazenar credenciais em um arquivo de script, você deverá proteger o arquivo para impedir acesso não autorizado.</span><span class="sxs-lookup"><span data-stu-id="b457d-126">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
    -   <span data-ttu-id="b457d-127">(Opcional) Use **- c** para fazer uma comparação no nível de coluna.</span><span class="sxs-lookup"><span data-stu-id="b457d-127">(Optional) Use **-c** to do a column-level comparison.</span></span>  
  
    -   <span data-ttu-id="b457d-128">(Opcional) Use **- q** para fazer uma rápida contagem somente de linhas e esquema.</span><span class="sxs-lookup"><span data-stu-id="b457d-128">(Optional) Use **-q** to do a fast, row count- and schema-only comparison.</span></span>  
  
    -   <span data-ttu-id="b457d-129">(Opcional) Especifique um nome de arquivo e caminho para **- o** para a saída dos resultados em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="b457d-129">(Optional) Specify a file name and path for **-o** to output the results to a file.</span></span>  
  
    -   <span data-ttu-id="b457d-130">(Opcional) Especifique uma tabela no banco de dados de assinatura para inserir resultados de **- et**.</span><span class="sxs-lookup"><span data-stu-id="b457d-130">(Optional) Specify a table in the subscription database into which to insert results for **-et**.</span></span> <span data-ttu-id="b457d-131">Se a tabela já existir, especifique **- dt** para cancelar primeiro a tabela.</span><span class="sxs-lookup"><span data-stu-id="b457d-131">If the table already exists, specify **-dt** to first drop the table.</span></span>  
  
    -   <span data-ttu-id="b457d-132">(Opcional) Use **-f** para gerar um arquivo [!INCLUDE[tsql](../../../includes/tsql-md.md)] para corrigir os dados no Assinante e corresponderem aos dados do Publicador.</span><span class="sxs-lookup"><span data-stu-id="b457d-132">(Optional) Use **-f** to generate a [!INCLUDE[tsql](../../../includes/tsql-md.md)] file to fix data at the Subscriber so that it matches data at the Publisher.</span></span> <span data-ttu-id="b457d-133">Use **- df** para especificar o número de instruções [!INCLUDE[tsql](../../../includes/tsql-md.md)] em cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="b457d-133">Use **-df** to specify the number of [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements in each file.</span></span>  
  
    -   <span data-ttu-id="b457d-134">(Opcional) Use **- rc** e **- ri** para especificar o número de horas para repetir uma operação e o intervalo de repetição.</span><span class="sxs-lookup"><span data-stu-id="b457d-134">(Optional) Use **-rc** and **-ri** to specify the number of times to retry an operation and the retry interval.</span></span>  
  
    -   <span data-ttu-id="b457d-135">(Opcional) Use **- strict** para impor uma comparação de esquema estrita entre tabelas de origem e destino.</span><span class="sxs-lookup"><span data-stu-id="b457d-135">(Optional) Use **-strict** to enforce strict schema comparison between source and destination tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b457d-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b457d-136">See Also</span></span>  
 [<span data-ttu-id="b457d-137">Validar dados no assinante</span><span class="sxs-lookup"><span data-stu-id="b457d-137">Validate Data at the Subscriber</span></span>](../validate-data-at-the-subscriber.md)  
  
  
