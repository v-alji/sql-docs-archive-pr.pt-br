---
title: Destino do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlserverdest.f1
helpviewer_keywords:
- SQL Server destination
- loading data
- destinations [Integration Services], SQL Server
- inserting data
- bulk load [Integration Services]
ms.assetid: a0227cd8-6944-4547-87e8-7b2507e26442
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fcd65007e1e6af36386cb2ceba1f7242305b81a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679452"
---
# <a name="sql-server-destination"></a><span data-ttu-id="e9829-102">destino do SQL Server</span><span class="sxs-lookup"><span data-stu-id="e9829-102">SQL Server Destination</span></span>
  <span data-ttu-id="e9829-103">O destino do SQL Server conecta-se a um banco de dados local do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e efetua carregamentos de dados em massa em tabelas e modos de exibição do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9829-103">The SQL Server destination connects to a local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database and bulk loads data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables and views.</span></span> <span data-ttu-id="e9829-104">Não é possível usar o destino do SQL Server em pacotes que acessam um banco de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em um servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="e9829-104">You cannot use the SQL Server destination in packages that access a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database on a remote server.</span></span> <span data-ttu-id="e9829-105">Em vez disso, os pacotes devem usar o destino OLE DB.</span><span class="sxs-lookup"><span data-stu-id="e9829-105">Instead, the packages should use the OLE DB destination.</span></span> <span data-ttu-id="e9829-106">Para obter mais informações, consulte [OLE DB Destination](ole-db-destination.md).</span><span class="sxs-lookup"><span data-stu-id="e9829-106">For more information, see [OLE DB Destination](ole-db-destination.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="e9829-107">Permissões</span><span class="sxs-lookup"><span data-stu-id="e9829-107">Permissions</span></span>  
 <span data-ttu-id="e9829-108">Usuários que executam pacotes que incluem o destino do SQL Server precisam da permissão "Criar objetos globais".</span><span class="sxs-lookup"><span data-stu-id="e9829-108">Users who execute packages that include the SQL Server destination require the "Create global objects" permission.</span></span> <span data-ttu-id="e9829-109">Você pode conceder esta permissão aos usuários usando a ferramenta Política de Segurança Local, aberta no menu **Ferramentas Administrativas** .</span><span class="sxs-lookup"><span data-stu-id="e9829-109">You can grant this permission to users by using the Local Security Policy tool opened from the **Administrative Tools** menu.</span></span> <span data-ttu-id="e9829-110">Se você receber uma mensagem de erro ao executar um pacote que usa o destino do SQL Server, assegure-se de que a conta que executa o pacote tenha a permissão "Criar objetos globais".</span><span class="sxs-lookup"><span data-stu-id="e9829-110">If you receive an error message when executing a package that uses the SQL Server destination, make sure that the account running the package has the "Create global objects" permission.</span></span>  
  
## <a name="bulk-inserts"></a><span data-ttu-id="e9829-111">Inserções em massa</span><span class="sxs-lookup"><span data-stu-id="e9829-111">Bulk Inserts</span></span>  
 <span data-ttu-id="e9829-112">Se tentar usar o destino do SQL Server para carregar dados em massa em um banco de dados de um SQL Server remoto, você poderá ver uma mensagem de erro semelhante à seguinte: "Um registro OLE DB está disponível.</span><span class="sxs-lookup"><span data-stu-id="e9829-112">If you attempt to use the SQL Server destination to bulk load data into a remote SQL Server database, you may see an error message similar to the following: "An OLE DB record is available.</span></span> <span data-ttu-id="e9829-113">Fonte: "Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client" Hresult: 0x80040E14 Descrição: “Não foi possível fazer o carregamento em massa porque o objeto de mapeamento de arquivo SSIS 'Global\DTSQLIMPORT ' não pôde ser aberto.</span><span class="sxs-lookup"><span data-stu-id="e9829-113">Source: "Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client" Hresult: 0x80040E14 Description: "Could not bulk load because SSIS file mapping object 'Global\DTSQLIMPORT ' could not be opened.</span></span> <span data-ttu-id="e9829-114">Erro de sistema operacional código 2 (O sistema não pode achar o arquivo especificado.).</span><span class="sxs-lookup"><span data-stu-id="e9829-114">Operating system error code 2 (The system cannot find the file specified.).</span></span> <span data-ttu-id="e9829-115">Certifique-se de estar acessando um servidor local via "segurança do Windows."</span><span class="sxs-lookup"><span data-stu-id="e9829-115">Make sure you are accessing a local server via Windows security.""</span></span>  
  
 <span data-ttu-id="e9829-116">O destino do SQL Server oferece a mesma inserção de dados em alta velocidade no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que a tarefa de Inserção em Massa fornece, porém, usando o destino do SQL Server, você pode aplicar transformações em dados de coluna antes de os dados serem carregados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9829-116">The SQL Server destination offers the same high-speed insertion of data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that the Bulk Insert task provides; however, by using the SQL Server destination, a package can apply transformations to column data before the data is loaded into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e9829-117">Para carregar dados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], deve-se considerar o uso do destino do SQL Server em vez do destino do OLE DB.</span><span class="sxs-lookup"><span data-stu-id="e9829-117">For loading data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you should consider using the SQL Server destination instead of the OLE DB destination.</span></span>  
  
### <a name="bulk-insert-options"></a><span data-ttu-id="e9829-118">Opções de inserção de massa</span><span class="sxs-lookup"><span data-stu-id="e9829-118">Bulk Insert Options</span></span>  
 <span data-ttu-id="e9829-119">Se o destino do SQL Server usar um modo de acesso de dados da carga-rápida, você poderá especificar as seguintes opções de carga rápida:</span><span class="sxs-lookup"><span data-stu-id="e9829-119">If the SQL Server destination uses a fast-load data access mode, you can specify the following fast load options:</span></span>  
  
-   <span data-ttu-id="e9829-120">Reter valores de identidade do arquivo de dados importado ou usar valores exclusivos atribuídos por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9829-120">Retain identity values from the imported data file, or use unique values assigned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="e9829-121">Reter valores nulos durante a operação de carregamento em massa.</span><span class="sxs-lookup"><span data-stu-id="e9829-121">Retain null values during the bulk load operation.</span></span>  
  
-   <span data-ttu-id="e9829-122">Verificar restrições na tabela de destino ou exibir durante a operação de importação em massa.</span><span class="sxs-lookup"><span data-stu-id="e9829-122">Verify constraints on the target table or view during the bulk import operation.</span></span>  
  
-   <span data-ttu-id="e9829-123">Adquirir um bloqueio em nível de tabela pela duração da operação de carregamento em massa.</span><span class="sxs-lookup"><span data-stu-id="e9829-123">Acquire a table-level lock for the duration of the bulk load operation.</span></span>  
  
-   <span data-ttu-id="e9829-124">Executar disparadores de inserção definidos na tabela de destino durante a operação de carregamento em massa.</span><span class="sxs-lookup"><span data-stu-id="e9829-124">Execute insert triggers defined on the destination table during the bulk load operation.</span></span>  
  
-   <span data-ttu-id="e9829-125">Especificar o número da primeira linha na entrada a ser carregada durante a operação de inserção em massa.</span><span class="sxs-lookup"><span data-stu-id="e9829-125">Specify the number of the first row in the input to load during the bulk insert operation.</span></span>  
  
-   <span data-ttu-id="e9829-126">Especificar o número da última linha na entrada a ser carregada durante a operação de inserção em massa.</span><span class="sxs-lookup"><span data-stu-id="e9829-126">Specify the number of the last row in the input to load during the bulk insert operation.</span></span>  
  
-   <span data-ttu-id="e9829-127">Especificar o número máximo de erros permitidos antes que a operação de inserção em massa seja cancelada.</span><span class="sxs-lookup"><span data-stu-id="e9829-127">Specify the maximum number of errors allowed before the bulk load operation is canceled.</span></span> <span data-ttu-id="e9829-128">Cada linha que não puder ser importada será contada como um erro.</span><span class="sxs-lookup"><span data-stu-id="e9829-128">Each row that cannot be imported is counted as one error.</span></span>  
  
-   <span data-ttu-id="e9829-129">Especificar as colunas na entrada que contêm dados ordenados.</span><span class="sxs-lookup"><span data-stu-id="e9829-129">Specify the columns in the input that contain sorted data.</span></span>  
  
 <span data-ttu-id="e9829-130">Para obter mais informações sobre as opções de carregamento em massa, consulte [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e9829-130">For more information about bulk load options, see [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
#### <a name="performance-improvements"></a><span data-ttu-id="e9829-131">Melhorias no desempenho</span><span class="sxs-lookup"><span data-stu-id="e9829-131">Performance Improvements</span></span>  
 <span data-ttu-id="e9829-132">Para melhorar o desempenho de uma inserção de massa e o acesso aos dados de tabela durante a operação de inserção em massa, você deve alterar as opções padrão conforme o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e9829-132">To improve the performance of a bulk insert and the access to table data during the bulk insert operation, you should change the default options as follows:</span></span>  
  
-   <span data-ttu-id="e9829-133">Não verificar restrições na tabela de destino ou exibir durante a operação de importação em massa.</span><span class="sxs-lookup"><span data-stu-id="e9829-133">Do not verify constraints on the target table or view during the bulk import operation.</span></span>  
  
-   <span data-ttu-id="e9829-134">Não executar disparadores de inserção definidos na tabela de destino durante a operação de carregamento em massa.</span><span class="sxs-lookup"><span data-stu-id="e9829-134">Do not execute insert triggers defined on the destination table during the bulk load operation.</span></span>  
  
-   <span data-ttu-id="e9829-135">Não aplicar um bloqueio à tabela.</span><span class="sxs-lookup"><span data-stu-id="e9829-135">Do not apply a lock to the table.</span></span> <span data-ttu-id="e9829-136">Desse modo, a tabela permanece disponível para outros usuários e aplicativos durante a operação de inserção em massa.</span><span class="sxs-lookup"><span data-stu-id="e9829-136">That way, the table remains available to other users and applications during the bulk insert operation.</span></span>  
  
## <a name="configuration-of-the-sql-server-destination"></a><span data-ttu-id="e9829-137">Configuração do destino do SQL Server</span><span class="sxs-lookup"><span data-stu-id="e9829-137">Configuration of the SQL Server Destination</span></span>  
 <span data-ttu-id="e9829-138">É possível configurar o destino do SQL Server das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="e9829-138">You can configure the SQL Server destination in the following ways:</span></span>  
  
-   <span data-ttu-id="e9829-139">Especificar a tabela ou exibir em qual carregar os dados em massa.</span><span class="sxs-lookup"><span data-stu-id="e9829-139">Specify the table or view into which to bulk load the data.</span></span>  
  
-   <span data-ttu-id="e9829-140">Personalizar a operação de carregamento em massa especificando opções como verificar restrições ou não.</span><span class="sxs-lookup"><span data-stu-id="e9829-140">Customize the bulk load operation by specifying options such as whether to check constraints.</span></span>  
  
-   <span data-ttu-id="e9829-141">Especificar se todas as linhas confirmam em um lote ou definem o número de máximo de linhas para confirmar como um lote.</span><span class="sxs-lookup"><span data-stu-id="e9829-141">Specify whether all rows commit in one batch or set the maximum number of rows to commit as a batch.</span></span>  
  
-   <span data-ttu-id="e9829-142">Especificar um tempo-limite para a operação de carregamento em massa.</span><span class="sxs-lookup"><span data-stu-id="e9829-142">Specify a time-out for the bulk load operation.</span></span>  
  
 <span data-ttu-id="e9829-143">Esse destino usa um gerenciador de conexões OLE DB para conectar-se a uma fonte de dados e o gerenciador de conexões especifica o provedor OLE DB a ser usado.</span><span class="sxs-lookup"><span data-stu-id="e9829-143">This destination uses an OLE DB connection manager to connect to a data source, and the connection manager specifies the OLE DB provider to use.</span></span> <span data-ttu-id="e9829-144">Para obter mais informações, consulte [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e9829-144">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
 <span data-ttu-id="e9829-145">Um projeto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] também fornece o objeto de fonte de dados do qual se pode criar um administrador de conexão OLE DB.</span><span class="sxs-lookup"><span data-stu-id="e9829-145">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project also provides the data source object from which you can create an OLE DB connection manager.</span></span> <span data-ttu-id="e9829-146">Isto torna as fontes de dados e exibições de fontes de dados disponíveis para o destino do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e9829-146">This makes data sources and data source views available to the SQL Server destination.</span></span>  
  
 <span data-ttu-id="e9829-147">O destino do SQL Server tem uma entrada.</span><span class="sxs-lookup"><span data-stu-id="e9829-147">The SQL Server destination has one input.</span></span> <span data-ttu-id="e9829-148">Não dá suporte a uma saída de erro.</span><span class="sxs-lookup"><span data-stu-id="e9829-148">It does not support an error output.</span></span>  
  
 <span data-ttu-id="e9829-149">Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.</span><span class="sxs-lookup"><span data-stu-id="e9829-149">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="e9829-150">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor de Destino do SQL Server**, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="e9829-150">For more information about the properties that you can set in the **SQL Server Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e9829-151">Editor de Destinos SQL &#40;página Gerenciador de Conexões&#41;</span><span class="sxs-lookup"><span data-stu-id="e9829-151">SQL Destination Editor &#40;Connection Manager Page&#41;</span></span>](../sql-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="e9829-152">Editor de Destinos SQL &#40;página Mapeamentos&#41;</span><span class="sxs-lookup"><span data-stu-id="e9829-152">SQL Destination Editor &#40;Mappings Page&#41;</span></span>](../sql-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="e9829-153">Editor de Destinos SQL &#40;página Avançado&#41;</span><span class="sxs-lookup"><span data-stu-id="e9829-153">SQL Destination Editor &#40;Advanced Page&#41;</span></span>](../sql-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="e9829-154">A caixa de diálogo **Editor Avançado** reflete as propriedades que podem ser definidas programaticamente.</span><span class="sxs-lookup"><span data-stu-id="e9829-154">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="e9829-155">Para obter mais informações sobre as propriedades que podem ser definidas na caixa de diálogo **Editor Avançado** ou programaticamente, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="e9829-155">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e9829-156">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="e9829-156">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="e9829-157">Propriedades personalizadas do destino SQL Server</span><span class="sxs-lookup"><span data-stu-id="e9829-157">SQL Server Destination Custom Properties</span></span>](sql-server-destination-custom-properties.md)  
  
 <span data-ttu-id="e9829-158">Para obter mais informações sobre como definir propriedades, clique em um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="e9829-158">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e9829-159">Carregar dados em massa por meio do destino do SQL Server</span><span class="sxs-lookup"><span data-stu-id="e9829-159">Bulk Load Data by Using the SQL Server Destination</span></span>](sql-server-destination.md)  
  
-   [<span data-ttu-id="e9829-160">Definir as propriedades de um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="e9829-160">Set the Properties of a Data Flow Component</span></span>](set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="e9829-161">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="e9829-161">Related Tasks</span></span>  
  
-   [<span data-ttu-id="e9829-162">Carregar dados em massa por meio do destino do SQL Server</span><span class="sxs-lookup"><span data-stu-id="e9829-162">Bulk Load Data by Using the SQL Server Destination</span></span>](sql-server-destination.md)  
  
-   [<span data-ttu-id="e9829-163">Definir as propriedades de um componente de fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="e9829-163">Set the Properties of a Data Flow Component</span></span>](set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-content"></a><span data-ttu-id="e9829-164">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="e9829-164">Related Content</span></span>  
  
-   <span data-ttu-id="e9829-165">Artigo técnico, [You may get "Unable to prepare the SSIS bulk insert for data insertion" error on UAC enabled systems](https://go.microsoft.com/fwlink/?LinkId=199482), em support.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e9829-165">Technical article, [You may get "Unable to prepare the SSIS bulk insert for data insertion" error on UAC enabled systems](https://go.microsoft.com/fwlink/?LinkId=199482), on support.microsoft.com.</span></span>  
  
-   <span data-ttu-id="e9829-166">Artigo técnico, [The Data Loading Performance Guide](https://go.microsoft.com/fwlink/?LinkId=233700), em msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e9829-166">Technical article, [The Data Loading Performance Guide](https://go.microsoft.com/fwlink/?LinkId=233700), on msdn.microsoft.com.</span></span>  
  
-   <span data-ttu-id="e9829-167">Artigo técnico, [Using SQL Server Integration Services to Bulk Load Data](https://go.microsoft.com/fwlink/?LinkId=233701)(Usando o SQL Server Integration Services para carregar dados em massa), em simple-talk.com.</span><span class="sxs-lookup"><span data-stu-id="e9829-167">Technical article, [Using SQL Server Integration Services to Bulk Load Data](https://go.microsoft.com/fwlink/?LinkId=233701), on simple-talk.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9829-168">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e9829-168">See Also</span></span>  
 [<span data-ttu-id="e9829-169">Fluxo de Dados</span><span class="sxs-lookup"><span data-stu-id="e9829-169">Data Flow</span></span>](data-flow.md)  
  
  
