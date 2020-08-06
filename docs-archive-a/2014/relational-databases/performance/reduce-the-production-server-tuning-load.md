---
title: Reduzir a carga de ajuste do servidor de produção | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- overhead [Database Engine Tuning Advisor]
- tuning overhead [SQL Server]
- reducing production server tuning load
- Database Engine Tuning Advisor [SQL Server], test servers
- test servers [Database Engine Tuning Advisor]
- production servers [SQL Server]
- offload tuning overhead [SQL Server]
ms.assetid: bb95ecaf-444a-4771-a625-e0a91c8f0709
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 53a61b17793a50d6b819f7c1684afdc4de4377f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575785"
---
# <a name="reduce-the-production-server-tuning-load"></a><span data-ttu-id="daf13-102">Reduzir a carga de ajuste do servidor de produção</span><span class="sxs-lookup"><span data-stu-id="daf13-102">Reduce the Production Server Tuning Load</span></span>
  [!INCLUDE[ssDE](../../../includes/ssde-md.md)] <span data-ttu-id="daf13-103">O Orientador de Otimização usa o otimizador de consulta para analisar uma carga de trabalho e fazer recomendações de ajuste.</span><span class="sxs-lookup"><span data-stu-id="daf13-103">Tuning Advisor relies on the query optimizer to analyze a workload and to make tuning recommendations.</span></span> <span data-ttu-id="daf13-104">Executar essa análise no servidor de produção aumenta a carga do servidor e pode prejudicar o desempenho do servidor durante a sessão de ajuste.</span><span class="sxs-lookup"><span data-stu-id="daf13-104">Performing this analysis on the production server adds to the server load and can hurt server performance during the tuning session.</span></span> <span data-ttu-id="daf13-105">É possível diminuir o impacto na carga do servidor durante uma sessão de ajuste usando um servidor de teste além do servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="daf13-105">You can reduce the impact to the server load during a tuning session by using a test server in addition to the production server.</span></span>

## <a name="how-database-engine-tuning-advisor-uses-a-test-server"></a><span data-ttu-id="daf13-106">Como o Orientador de Otimização de Mecanismo de Banco de Dados usa um servidor de teste</span><span class="sxs-lookup"><span data-stu-id="daf13-106">How Database Engine Tuning Advisor Uses a Test Server</span></span>
 <span data-ttu-id="daf13-107">O modo tradicional de uso de um servidor de teste é copiar todos os dados de seu servidor de produção no servidor de teste, ajustar o servidor de teste e depois implementar a recomendação no seu servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="daf13-107">The traditional way to use a test server is to copy all of the data from your production server to your test server, tune the test server, and then implement the recommendation on your production server.</span></span> <span data-ttu-id="daf13-108">Esse processo elimina o impacto de desempenho em seu servidor de produção, mas, mesmo assim, não é a melhor solução.</span><span class="sxs-lookup"><span data-stu-id="daf13-108">This process eliminates the performance impact on your production server, but nevertheless is not the optimal solution.</span></span> <span data-ttu-id="daf13-109">Por exemplo, copiar grandes volumes de dados da produção no servidor de teste pode consumir tempo e recursos significativos.</span><span class="sxs-lookup"><span data-stu-id="daf13-109">For example, copying large amounts of data from the production to the test server can consume substantial amounts of time and resources.</span></span> <span data-ttu-id="daf13-110">Além disso, o hardware do servidor de teste raramente é tão eficiente quanto o hardware implantado nos servidores de produção.</span><span class="sxs-lookup"><span data-stu-id="daf13-110">In addition, test server hardware is seldom as powerful as the hardware that is deployed for production servers.</span></span> <span data-ttu-id="daf13-111">O processo de ajuste depende do otimizador de consulta, e as recomendações geradas são, em parte, baseadas no hardware subjacente.</span><span class="sxs-lookup"><span data-stu-id="daf13-111">The tuning process relies on the query optimizer, and the recommendations it generates are based in part on the underlying hardware.</span></span> <span data-ttu-id="daf13-112">Se o hardware dos servidores de teste e de produção não for idêntico, a qualidade da recomendação do Orientador de Otimização do [!INCLUDE[ssDE](../../../includes/ssde-md.md)] será menor.</span><span class="sxs-lookup"><span data-stu-id="daf13-112">If the test and production server hardware are not identical, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor recommendation quality is diminished.</span></span>

 <span data-ttu-id="daf13-113">Para evitar problemas desse tipo, o Orientador de Otimização do Mecanismo do [!INCLUDE[ssDE](../../../includes/ssde-md.md)] ajusta um banco de dados em um servidor de produção descarregando a maioria da carga de ajuste em um servidor de teste.</span><span class="sxs-lookup"><span data-stu-id="daf13-113">To avoid these problems, [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor tunes a database on a production server by offloading most of the tuning load onto a test server.</span></span> <span data-ttu-id="daf13-114">Ele faz isso usando as informações de configuração de hardware do servidor de produção, sem, de fato, copiar os dados do servidor de produção no servidor de teste.</span><span class="sxs-lookup"><span data-stu-id="daf13-114">It does this by using the production server hardware configuration information and without actually copying the data from the production server to the test server.</span></span> [!INCLUDE[ssDE](../../../includes/ssde-md.md)] <span data-ttu-id="daf13-115">não copia dados reais do servidor de produção para o servidor de teste.</span><span class="sxs-lookup"><span data-stu-id="daf13-115">Tuning Advisor does not copy actual data from the production server to the test server.</span></span> <span data-ttu-id="daf13-116">Ele apenas copia os metadados e as estatísticas necessárias.</span><span class="sxs-lookup"><span data-stu-id="daf13-116">It only copies the metadata and necessary statistics.</span></span>

 <span data-ttu-id="daf13-117">As etapas seguintes esboçam o processo para ajustar um banco de dados de produção em um servidor de teste:</span><span class="sxs-lookup"><span data-stu-id="daf13-117">The following steps outline the process for tuning a production database on a test server:</span></span>

1.  <span data-ttu-id="daf13-118">Verifique se o usuário que deseja usar o servidor de teste existe nos dois servidores.</span><span class="sxs-lookup"><span data-stu-id="daf13-118">Make sure that the user who wants to use the test server exists on both servers.</span></span>

     <span data-ttu-id="daf13-119">Antes de começar, verifique se o usuário que deseja usar o servidor de teste para ajustar um banco de dados no servidor de produção existe em ambos os servidores.</span><span class="sxs-lookup"><span data-stu-id="daf13-119">Before you start, make sure that the user who wants to use the test server to tune a database on the production server exists on both servers.</span></span> <span data-ttu-id="daf13-120">Isso requer que você crie o usuário e o logon dele no servidor de teste.</span><span class="sxs-lookup"><span data-stu-id="daf13-120">This requires that you create the user and his or her login on the test server.</span></span> <span data-ttu-id="daf13-121">Se você for um membro da função de servidor fixa **sysadmin** nos dois computadores, essa etapa será desnecessária.</span><span class="sxs-lookup"><span data-stu-id="daf13-121">If you are a member of the **sysadmin** fixed server role on both computers, this step is not necessary.</span></span>

2.  <span data-ttu-id="daf13-122">Ajuste a carga de trabalho no servidor de teste.</span><span class="sxs-lookup"><span data-stu-id="daf13-122">Tune the workload on the test server.</span></span>

     <span data-ttu-id="daf13-123">Para ajustar a carga de trabalho em um servidor de teste,é necessário usar um arquivo de entrada XML com o utilitário de linha de comando **dta** .</span><span class="sxs-lookup"><span data-stu-id="daf13-123">To tune a workload on a test server, you must use an XML input file with the **dta** command-line utility.</span></span> <span data-ttu-id="daf13-124">No arquivo de entrada XML, especifique o nome de seu servidor de teste com o subelemento **TestServer** além de especificar os valores para os outros subelementos no elemento pai **TuningOptions** .</span><span class="sxs-lookup"><span data-stu-id="daf13-124">In the XML input file, specify the name of your test server with the **TestServer** subelement in addition to specifying the values for the other subelements under the **TuningOptions** parent element.</span></span>

     <span data-ttu-id="daf13-125">Durante o processo de ajuste, o Orientador de Otimização do Mecanismo do Banco de Dados cria um banco de dados shell no servidor de teste.</span><span class="sxs-lookup"><span data-stu-id="daf13-125">During the tuning process, Database Engine Tuning Advisor creates a shell database on the test server.</span></span> <span data-ttu-id="daf13-126">Para criar esse banco de dados shell e ajustá-lo, o Orientador de Otimização do Mecanismo do Banco de Dados faz chamadas ao servidor de produção para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="daf13-126">To create this shell database and tune it, Database Engine Tuning Advisor makes calls to the production server for the following:</span></span>

    1.  [!INCLUDE[ssDE](../../../includes/ssde-md.md)] <span data-ttu-id="daf13-127">O Orientador de Otimização importa metadados do banco de dados de produção para o banco de dados shell do servidor de teste.</span><span class="sxs-lookup"><span data-stu-id="daf13-127">Tuning Advisor imports metadata from the production database to the test server shell database.</span></span> <span data-ttu-id="daf13-128">Esses metadados incluem tabelas vazias, índices, exibições, procedimentos armazenados, disparadores, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="daf13-128">This metadata includes empty tables, indexes, views, stored procedures, triggers, and so on.</span></span> <span data-ttu-id="daf13-129">Isso possibilita a execução de consultas de carga de trabalho no banco de dados shell do servidor de teste.</span><span class="sxs-lookup"><span data-stu-id="daf13-129">This makes it possible for the workload queries to execute against the test server shell database.</span></span>

    2.  [!INCLUDE[ssDE](../../../includes/ssde-md.md)] <span data-ttu-id="daf13-130">O Orientador de Otimização importa estatísticas do servidor de produção para que o otimizador de consulta possa otimizar as consultas com precisão no servidor de teste.</span><span class="sxs-lookup"><span data-stu-id="daf13-130">Tuning Advisor imports statistics from the production server so the query optimizer can accurately optimize queries on the test server.</span></span>

    3.  [!INCLUDE[ssDE](../../../includes/ssde-md.md)] <span data-ttu-id="daf13-131">O Orientador de Otimização importa parâmetros de hardware que especificam o número de processadores e a memória disponível do servidor de produção para fornecer ao otimizador de consulta as informações necessárias para gerar um plano de consulta.</span><span class="sxs-lookup"><span data-stu-id="daf13-131">Tuning Advisor imports hardware parameters specifying the number of processors and available memory from the production server to provide the query optimizer with the information it needs to generate a query plan.</span></span>

3.  <span data-ttu-id="daf13-132">Depois que o Orientador de Otimização do [!INCLUDE[ssDE](../../../includes/ssde-md.md)] termina de ajustar o banco de dados shell do servidor de teste, ele gera uma recomendação de ajuste.</span><span class="sxs-lookup"><span data-stu-id="daf13-132">After [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor finishes tuning the test server shell database, it generates a tuning recommendation.</span></span>

4.  <span data-ttu-id="daf13-133">Aplique a recomendação recebida para ajustar o servidor de teste ao servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="daf13-133">Apply the recommendation received from tuning the test server to the production server.</span></span>

 <span data-ttu-id="daf13-134">A ilustração a seguir mostra o servidor de teste e o cenário do servidor de produção:</span><span class="sxs-lookup"><span data-stu-id="daf13-134">The following illustration shows the test server and production server scenario:</span></span>

 <span data-ttu-id="daf13-135">![Uso do servidor de teste do Orientador de Otimização do Mecanismo de Banco de Dados](../../database-engine/media/testsvr.gif "Uso do servidor de teste do Orientador de Otimização do Mecanismo de Banco de Dados")</span><span class="sxs-lookup"><span data-stu-id="daf13-135">![Database Engine Tuning Advisor test server usage](../../database-engine/media/testsvr.gif "Database Engine Tuning Advisor test server usage")</span></span>

> [!NOTE]
>  <span data-ttu-id="daf13-136">O recurso de ajuste do servidor de teste não é suportado na interface gráfica de usuário do Orientador de Otimização do [!INCLUDE[ssDE](../../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="daf13-136">The test server tuning feature is not supported in the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor graphical user interface (GUI).</span></span>

## <a name="example"></a><span data-ttu-id="daf13-137">Exemplo</span><span class="sxs-lookup"><span data-stu-id="daf13-137">Example</span></span>
 <span data-ttu-id="daf13-138">Primeiro, verifique se o usuário que deseja executar o ajuste existe nos servidores de produção e no de teste.</span><span class="sxs-lookup"><span data-stu-id="daf13-138">First, make sure that the user who wants to perform the tuning exists on both the test and production servers.</span></span>

 <span data-ttu-id="daf13-139">Depois que as informações de usuário são copiadas no servidor de teste, você pode definir a sessão de ajuste do servidor de teste no arquivo de entrada XML do Orientador de Otimização do [!INCLUDE[ssDE](../../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="daf13-139">After the user information is copied over to your test server, you can define your test server tuning session in the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor XML input file.</span></span> <span data-ttu-id="daf13-140">O exemplo de arquivo de entrada XML a seguir ilustra como especificar um servidor de teste para ajustar um banco de dados com o Orientador de Otimização do [!INCLUDE[ssDE](../../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="daf13-140">The following example XML input file illustrates how to specify a test server to tune a database with [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor.</span></span>

 <span data-ttu-id="daf13-141">Neste exemplo, o banco de dados `MyDatabaseName` está sendo ajustado no `MyServerName`.</span><span class="sxs-lookup"><span data-stu-id="daf13-141">In this example, the `MyDatabaseName` database is being tuned on `MyServerName`.</span></span> <span data-ttu-id="daf13-142">O script [!INCLUDE[tsql](../../includes/tsql-md.md)] , `MyWorkloadScript.sql`, é usado como a carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="daf13-142">The [!INCLUDE[tsql](../../includes/tsql-md.md)] script, `MyWorkloadScript.sql`, is used as the workload.</span></span> <span data-ttu-id="daf13-143">Essa carga de trabalho contém eventos que são executados no `MyDatabaseName`.</span><span class="sxs-lookup"><span data-stu-id="daf13-143">This workload contains events that execute against `MyDatabaseName`.</span></span> <span data-ttu-id="daf13-144">A maioria das chamadas de otimizador de consulta a esse banco de dados, que acontecem como parte do processo de ajuste, é controlada pelo banco de dados shell que reside no `MyTestServerName`.</span><span class="sxs-lookup"><span data-stu-id="daf13-144">Most of the query optimizer calls to this database, which occur as part of the tuning process, are handled by the shell database that resides on `MyTestServerName`.</span></span> <span data-ttu-id="daf13-145">O banco de dados shell é composto de metadados e estatísticas.</span><span class="sxs-lookup"><span data-stu-id="daf13-145">The shell database is composed of metadata and statistics.</span></span> <span data-ttu-id="daf13-146">Esse processo resulta na sobrecarga do ajuste sendo descarregada no servidor de teste.</span><span class="sxs-lookup"><span data-stu-id="daf13-146">This process results in the tuning overhead being offloaded to the test server.</span></span> <span data-ttu-id="daf13-147">Quando o Orientador de Otimização do [!INCLUDE[ssDE](../../../includes/ssde-md.md)] gera a recomendação de ajuste usando esse arquivo de entrada XML, ele deve considerar somente índices (`<FeatureSet>IDX</FeatureSet>`) , nenhum particionamento e não deve manter nenhuma estrutura de design físico existente em `MyDatabaseName`.</span><span class="sxs-lookup"><span data-stu-id="daf13-147">When [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Tuning Advisor generates its tuning recommendation using this XML input file, it should consider indexes only (`<FeatureSet>IDX</FeatureSet>`), no partitioning, and need not keep any of the existing physical design structures in `MyDatabaseName`.</span></span>

```
<?xml version="1.0" encoding="utf-16" ?>
<DTAXML xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="https://schemas.microsoft.com/sqlserver/2004/07/dta">
  <DTAInput>
    <Server>
      <Name>MyServerName</Name>
      <Database>
        <Name>MyDatabaseName</Name>
      </Database>
    </Server>
    <Workload>
      <File>MyWorkloadScript.sql</File>
    </Workload>
    <TuningOptions>
      <TestServer>MyTestServerName</TestServer>
      <FeatureSet>IDX</FeatureSet>
      <Partitioning>NONE</Partitioning>
      <KeepExisting>NONE</KeepExisting>
    </TuningOptions>
  </DTAInput>
</DTAXML>
```

## <a name="see-also"></a><span data-ttu-id="daf13-148">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="daf13-148">See Also</span></span>
 <span data-ttu-id="daf13-149">[Considerações para usar a referência de arquivo de entrada XML de servidores de teste](considerations-for-using-test-servers.md) [&#40;Orientador de otimização do mecanismo de banco de dados&#41;](database-engine-tuning-advisor.md)</span><span class="sxs-lookup"><span data-stu-id="daf13-149">[Considerations for Using Test Servers](considerations-for-using-test-servers.md) [XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](database-engine-tuning-advisor.md)</span></span>


