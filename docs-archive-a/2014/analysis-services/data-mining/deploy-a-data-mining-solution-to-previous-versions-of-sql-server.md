---
title: Implantar uma solução de mineração de dados em versões anteriores do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- backward compatibility [Analysis Services]
- holdout [data mining]
- deploy [Analysis Services]
- time series [Analysis Services]
- deploying [Analysis Services - data mining]
- synchronization [Analysis Services]
- deployment [Analysis Services]
ms.assetid: 2715c245-f206-43af-8bf5-e6bd2585477a
author: minewiskan
ms.author: owend
ms.openlocfilehash: f09a37c078cf58f24db9a08e3ddcb68cb2638717
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582213"
---
# <a name="deploy-a-data-mining-solution-to-previous-versions-of-sql-server"></a><span data-ttu-id="58cb9-102">Implantar uma solução de mineração de dados em versões anteriores do SQL Server</span><span class="sxs-lookup"><span data-stu-id="58cb9-102">Deploy a Data Mining Solution to Previous Versions of SQL Server</span></span>
  <span data-ttu-id="58cb9-103">Esta seção descreve problemas de compatibilidade conhecidos que podem surgir durante a tentativa de implantação de um modelo ou estrutura de mineração de dados criado em uma instância do [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] para um banco de dados que usa o SQL Server 2005 Analysis Services, ou quando você implanta modelos criados no SQL Server 2005 em uma instância do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58cb9-103">This section describes known compatibility issues that may arise when you attempt to deploy a data mining model or data mining structure that was created in an instance of [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] to a database that uses SQL Server 2005 Analysis Services, or when you deploy models created in SQL Server 2005 to an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="58cb9-104">A implantação em uma instância do SQL Server 2000 Analysis Services não é suportada.</span><span class="sxs-lookup"><span data-stu-id="58cb9-104">Deployment to an instance of SQL Server 2000 Analysis Services is not supported.</span></span>  
  
 [<span data-ttu-id="58cb9-105">Implantando modelos de série temporal</span><span class="sxs-lookup"><span data-stu-id="58cb9-105">Deploying Time Series Models</span></span>](#bkmk_TimeSeries)  
  
 [<span data-ttu-id="58cb9-106">Implantando modelos com controle</span><span class="sxs-lookup"><span data-stu-id="58cb9-106">Deploying Models with Holdout</span></span>](#bkmk_Holdout)  
  
 [<span data-ttu-id="58cb9-107">Implantando modelos com filtros</span><span class="sxs-lookup"><span data-stu-id="58cb9-107">Deploying Models with Filters</span></span>](#bkmk_Filter)  
  
 [<span data-ttu-id="58cb9-108">Restaurando de backups de banco de dados</span><span class="sxs-lookup"><span data-stu-id="58cb9-108">Restoring from Database Backups</span></span>](#bkmk_Backup)  
  
 [<span data-ttu-id="58cb9-109">Usando a sincronização de banco de dados</span><span class="sxs-lookup"><span data-stu-id="58cb9-109">Using Database Synchronization</span></span>](#bkmk_Synch)  
  
##  <a name="deploying-times-series-models"></a><a name="bkmk_TimeSeries"></a><span data-ttu-id="58cb9-110">Implantando modelos de série Times</span><span class="sxs-lookup"><span data-stu-id="58cb9-110">Deploying Times Series Models</span></span>  
 <span data-ttu-id="58cb9-111">O algoritmo MTS foi aprimorado no SQL Server 2008 com a adição de um segundo algoritmo complementar, o ARIMA.</span><span class="sxs-lookup"><span data-stu-id="58cb9-111">The Microsoft Time Series algorithm was enhanced in SQL Server 2008 by the addition of a second, complementary algorithm, ARIMA.</span></span> <span data-ttu-id="58cb9-112">Para obter mais informações sobre as alterações no algoritmo de série temporal, consulte [Algoritmo MTS](microsoft-time-series-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="58cb9-112">For more information about the changes in the time series algorithm, see [Microsoft Time Series Algorithm](microsoft-time-series-algorithm.md).</span></span>  
  
 <span data-ttu-id="58cb9-113">Portanto, os modelos de mineração de série temporal que usam o novo algoritmo ARIMA podem apresentar um comportamento diferente quando implantados em uma instância do SQL Server 2005 Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="58cb9-113">Therefore, time series mining models that use the new ARIMA algorithm may behave differently when deployed to an instance of SQL Server 2005 Analysis Services.</span></span>  
  
 <span data-ttu-id="58cb9-114">Se você tiver definido explicitamente o parâmetro PREDICTION_SMOOTHING para controlar a mistura dos modelos ARTXP e ARIMA na previsão, ao implantar este modelo em uma instância do SQL Server 2005, o Analysis Services gerará um erro declarando que o parâmetro não é válido.</span><span class="sxs-lookup"><span data-stu-id="58cb9-114">If you have explicitly set the parameter PREDICTION_SMOOTHING to control the mixture of ARTXP and ARIMA models in prediction, when you deploy this model to an instance of SQL Server 2005, Analysis Services will raise an error stating that the parameter is not valid.</span></span> <span data-ttu-id="58cb9-115">Para impedir esse erro, exclua o parâmetro PREDICTION_SMOOTHING e converta os modelos em um puro modelo ARTXP.</span><span class="sxs-lookup"><span data-stu-id="58cb9-115">To prevent this error, you must delete the PREDICTION_SMOOTHING parameter and convert the models to a pure ARTXP model.</span></span>  
  
 <span data-ttu-id="58cb9-116">Por outro lado, se você implantar um modelo de série temporal que foi criado com o SQL Server 2005 Analysis Services em uma instância do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], ao abrir o modelo de mineração do [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], os arquivos de definição serão primeiramente convertidos no novo formato e dois novos parâmetros serão adicionados, por padrão, a todos os modelos de série temporal.</span><span class="sxs-lookup"><span data-stu-id="58cb9-116">Conversely, if you deploy a time series model that was created using SQL Server 2005 Analysis Services to an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], when you open the mining model in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], the definition files are first converted to the new format, and two new parameters are added by default to all time series models.</span></span> <span data-ttu-id="58cb9-117">O parâmetro FORECAST_METHOD é adicionado com o valor padrão de MIXED e o parâmetro PREDICTION_SMOOTHING é adicionado com o valor padrão de 0,5.</span><span class="sxs-lookup"><span data-stu-id="58cb9-117">The parameter FORECAST_METHOD is added with the default value of MIXED, and the parameter PREDICTION_SMOOTHING is added with the default value of 0.5.</span></span> <span data-ttu-id="58cb9-118">Porém, o modelo continuará usando apenas ARTXP para fazer previsões até que o modelo seja reprocessado.</span><span class="sxs-lookup"><span data-stu-id="58cb9-118">However, the model will continue to use only ARTXP for forecasting until you reprocess the model.</span></span> <span data-ttu-id="58cb9-119">Assim que você reprocessa o modelo, a previsão muda para usar ARIMA e ARTXP.</span><span class="sxs-lookup"><span data-stu-id="58cb9-119">As soon as you reprocess the model, prediction changes to use both ARIMA and ARTXP.</span></span>  
  
 <span data-ttu-id="58cb9-120">Desse modo, se deseja evitar a alteração do modelo, apenas procure e nunca processe o modelo.</span><span class="sxs-lookup"><span data-stu-id="58cb9-120">Therefore, if you wish to avoid changing the model, you should only browse the model and never process it.</span></span> <span data-ttu-id="58cb9-121">Se preferir, defina explicitamente os parâmetros FORECAST_METHOD ou PREDICTION_SMOOTHING.</span><span class="sxs-lookup"><span data-stu-id="58cb9-121">Alternatively, you could explicitly set the FORECAST_METHOD or PREDICTION_SMOOTHING parameters.</span></span>  
  
 <span data-ttu-id="58cb9-122">Para obter informações detalhadas sobre como configurar modelos mistos, consulte [Referência técnica do algoritmo MTS](microsoft-time-series-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="58cb9-122">For detailed information about configuring mixed models, see [Microsoft Time Series Algorithm Technical Reference](microsoft-time-series-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="58cb9-123">Se o provedor usado para a fonte de dados do modelo for SQL Client Data Provider 10, você também deve modificar a definição de fonte de dados para especificar a versão anterior do SQL Server Native Client.</span><span class="sxs-lookup"><span data-stu-id="58cb9-123">If the provider that is used for the model's data source is SQL Client Data Provider 10, you must also modify the data source definition to specify the previous version of the SQL Server Native Client.</span></span> <span data-ttu-id="58cb9-124">Caso contrário, o [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] gera um erro que declara que o provedor não é registrado.</span><span class="sxs-lookup"><span data-stu-id="58cb9-124">Otherwise, [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] generates an error stating that the provider is not registered.</span></span>  
  
##  <a name="deploying-models-with-holdout"></a><a name="bkmk_Holdout"></a> <span data-ttu-id="58cb9-125">Implantando modelos com controle</span><span class="sxs-lookup"><span data-stu-id="58cb9-125">Deploying Models with Holdout</span></span>  
 <span data-ttu-id="58cb9-126">Se o [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] for usado para criar uma estrutura de mineração que contém uma partição de controle usada para testar modelos de mineração de dados, a estrutura de mineração poderá ser implantada em uma instância do SQL Server 2005, mas as informações de partição serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="58cb9-126">If you use [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] to create a mining structure that contains a holdout partition used for testing data mining models, the mining structure can be deployed to an instance of SQL Server 2005, but the partition information will be lost.</span></span>  
  
 <span data-ttu-id="58cb9-127">Ao abrir a estrutura de mineração no SQL Server 2005 Analysis Services, o [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] gera um erro e, em seguida, gera novamente a estrutura para remover a partição de controle.</span><span class="sxs-lookup"><span data-stu-id="58cb9-127">When you open the mining structure in SQL Server 2005 Analysis Services, [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] raises an error, and then regenerates the structure to remove the holdout partition.</span></span>  
  
 <span data-ttu-id="58cb9-128">Depois que a estrutura tiver sido recriada, o tamanho da partição de controle não estará mais disponível no janela Propriedades; no entanto, o valor \<ddl100_100:HoldoutMaxPercent> 30 \</ddl100_100:HoldoutMaxPercent> ) ainda pode estar presente no arquivo de script ASSL.</span><span class="sxs-lookup"><span data-stu-id="58cb9-128">After the structure has been rebuilt, the size of the holdout partition is no longer available in the Properties window; however, the value \<ddl100_100:HoldoutMaxPercent>30\</ddl100_100:HoldoutMaxPercent>) may still be present in the ASSL script file.</span></span>  
  
##  <a name="deploying-models-with-filters"></a><a name="bkmk_Filter"></a> <span data-ttu-id="58cb9-129">Implantando modelos com filtros</span><span class="sxs-lookup"><span data-stu-id="58cb9-129">Deploying Models with Filters</span></span>  
 <span data-ttu-id="58cb9-130">Se o [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] for usado para aplicar um filtro em um modelo de mineração, o modelo poderá ser implantado em uma instância do SQL Server 2005, mas o filtro não será aplicado.</span><span class="sxs-lookup"><span data-stu-id="58cb9-130">If you use [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] to apply a filter to a mining model, the model can be deployed to an instance of SQL Server 2005, but the filter will not be applied.</span></span>  
  
 <span data-ttu-id="58cb9-131">Quando você abre o modelo de mineração, o [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] gera um erro e, em seguida, gera novamente o modelo para remover o filtro.</span><span class="sxs-lookup"><span data-stu-id="58cb9-131">When you open the mining model, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] raises an error, and then regenerates the model to remove the filter.</span></span>  
  
##  <a name="restoring-from-database-backups"></a><a name="bkmk_Backup"></a><span data-ttu-id="58cb9-132">Restaurando de backups de banco de dados</span><span class="sxs-lookup"><span data-stu-id="58cb9-132">Restoring from Database Backups</span></span>  
 <span data-ttu-id="58cb9-133">Você não pode restaurar um backup de banco de dados que foi criado no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] para uma instância do SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="58cb9-133">You cannot restore a database backup that was created in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to an instance of SQL Server 2005.</span></span> <span data-ttu-id="58cb9-134">Se fizer isso, o SQL Server Management Studio gerará um erro.</span><span class="sxs-lookup"><span data-stu-id="58cb9-134">If you do so, SQL Server Management Studio generates an error.</span></span>  
  
 <span data-ttu-id="58cb9-135">Se você criar um backup de um banco de dados do SQL Server 2005 Analysis Services e restaurar esse backup em uma instância do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], todos os modelos de série temporal serão modificados conforme descrito na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="58cb9-135">If you create a backup of a SQL Server 2005 Analysis Services database and restore this backup on an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], all time series models are modified as described in the previous section.</span></span>  
  
##  <a name="using-database-synchronization"></a><a name="bkmk_Synch"></a><span data-ttu-id="58cb9-136">Usando a sincronização de banco de dados</span><span class="sxs-lookup"><span data-stu-id="58cb9-136">Using Database Synchronization</span></span>  
 <span data-ttu-id="58cb9-137">A sincronização do banco de dados não tem suporte do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] para o SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="58cb9-137">Database synchronization is not supported from [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to SQL Server 2005.</span></span>  
  
 <span data-ttu-id="58cb9-138">Se você tentar sincronizar um banco de dados [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , o servidor retornará um erro e a sincronização do banco de dados falhará.</span><span class="sxs-lookup"><span data-stu-id="58cb9-138">If you attempt to synchronize a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] database, the server returns an error and database synchronization fails.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58cb9-139">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="58cb9-139">See Also</span></span>  
 [<span data-ttu-id="58cb9-140">Analysis Services Backward Compatibility</span><span class="sxs-lookup"><span data-stu-id="58cb9-140">Analysis Services Backward Compatibility</span></span>](../analysis-services-backward-compatibility.md)  
  
  
