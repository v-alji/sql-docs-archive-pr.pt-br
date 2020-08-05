---
title: Inserir dados em parâmetros com valor de tabela | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters, inserting data into
ms.assetid: 9c1a3234-4675-40d3-b473-8df06208f880
author: rothja
ms.author: jroth
ms.openlocfilehash: 38e33c6e58bc2633591fa80e095ceafe46f67045
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572039"
---
# <a name="inserting-data-into-table-valued-parameters"></a><span data-ttu-id="c7bbd-102">Inserindo dados em parâmetros com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="c7bbd-102">Inserting Data into Table-Valued Parameters</span></span>
  <span data-ttu-id="c7bbd-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo dá suporte a dois modelos para o consumidor especificar dados para linhas de parâmetro com valor de tabela: um modelo de push e um modelo de pull.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider supports two models for the consumer to specify data for table valued parameter rows: a push model and a pull model.</span></span> <span data-ttu-id="c7bbd-104">Uma amostra que apresenta o modelo de pull está disponível; confira [Amostras de programação do SQL Server Data](https://msftdpprodsamples.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="c7bbd-104">A sample that demonstrates the pull model is available; see [SQL Server Data Programming Samples](https://msftdpprodsamples.codeplex.com/).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c7bbd-105">Uma coluna de parâmetro com valor de tabela deve ter valores não padrão em todas as linhas ou valores padrão em todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-105">A table-valued parameter column must have either non-default values in all rows or default values in all rows.</span></span> <span data-ttu-id="c7bbd-106">Não é possível ter valores padrão em algumas linhas, mas não em outras.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-106">It is not possible to have default values in some rows but not others.</span></span> <span data-ttu-id="c7bbd-107">Dessa forma, em associações de parâmetro com valor de tabela, os únicos valores de status permitidos para os dados da coluna do conjunto de linhas do parâmetro com valor de tabela são DBSTATUS_S_ISNULL e DBSTATUS_S_OK.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-107">Therefore, in table-valued parameter bindings, the only status values allowed for table-valued parameter rowset column data are DBSTATUS_S_ISNULL and DBSTATUS_S_OK.</span></span> <span data-ttu-id="c7bbd-108">DBSTATUS_S_DEFAULT resultará em falha e o valor de status associado será definido como DBSTATUS_E_BADSTATUS.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-108">DBSTATUS_S_DEFAULT will result in a failure and the bound status value will be set to DBSTATUS_E_BADSTATUS.</span></span>  
  
## <a name="push-model-loads-all-table-valued-paremeter-data-in-memory"></a><span data-ttu-id="c7bbd-109">Modelo de push (carrega todos os dados do parâmetro com valor de tabela na memória)</span><span class="sxs-lookup"><span data-stu-id="c7bbd-109">Push Model (Loads All Table-Valued Paremeter Data in Memory)</span></span>  
 <span data-ttu-id="c7bbd-110">O modelo de push é semelhante ao uso de conjuntos de parâmetro (ou seja, o parâmetro DBPARAMS em ICommand::Execute).</span><span class="sxs-lookup"><span data-stu-id="c7bbd-110">The push model is similar to the use of parameter sets (that is, the DBPARAMS parameter in ICommand::Execute).</span></span> <span data-ttu-id="c7bbd-111">O modelo de push só será usado se forem usados objetos de conjunto de linhas de parâmetro com valor de tabela sem uma implementação personalizada de interfaces IRowset.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-111">The push model is only used if table-valued parameter rowset objects are used without a customized implementation of IRowset interfaces.</span></span> <span data-ttu-id="c7bbd-112">O modelo de push é recomendado quando o número de linhas no conjunto de linhas do parâmetro com valor de tabela é pequeno e não se espera que uma pressão excessiva de memória seja colocada no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-112">The push model is recommended when the number of rows in the table-valued parameter rowset is small and is not expected to put excessive memory pressure on the application.</span></span> <span data-ttu-id="c7bbd-113">Esse modelo é mais simples do que o modelo de pull, pois não exige nenhuma outra funcionalidade do aplicativo do consumidor daquela que seja atualmente comum em aplicativos OLE DB típicos.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-113">This is simpler than the pull model, because it does not require any more functionality from the consumer application than what is currently common in typical OLE DB applications.</span></span>  
  
 <span data-ttu-id="c7bbd-114">Espera-se que o consumidor forneça todos os dados de parâmetro com valor de tabela ao provedor antes de executar um comando.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-114">The consumer is expected to provide all the table-valued parameter data to the provider before executing a command.</span></span> <span data-ttu-id="c7bbd-115">Para fornecer os dados, o consumidor popula um objeto do conjunto de linhas de parâmetro com valor de tabela para cada parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-115">To provide the data, the consumer populates a table-valued parameter rowset object for each table-valued parameter.</span></span> <span data-ttu-id="c7bbd-116">O objeto do conjunto de linhas de parâmetro com valor de tabela expõe operações Insert, Set e Delete do conjunto de linhas, que o consumidor usará para manipular os dados de parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-116">The table-valued parameter rowset object exposes rowset Insert, Set, and Delete operations, which the consumer will use to manipulate the table-valued parameter data.</span></span> <span data-ttu-id="c7bbd-117">O provedor buscará os dados do objeto do conjunto de linhas de parâmetro com valor de tabela em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-117">The provider will fetch the data from this table-valued parameter rowset object at execution time.</span></span>  
  
 <span data-ttu-id="c7bbd-118">Quando um objeto do conjunto de linhas de parâmetro com valor de tabela é fornecido ao consumidor, o consumidor pode processá-lo como um objeto do conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-118">When a table-valued parameter rowset object is provided to the consumer, the consumer can process it as a rowset object.</span></span> <span data-ttu-id="c7bbd-119">O consumidor pode obter as informações de tipo de cada coluna (tipo, comprimento máximo, precisão e escala) usando o método de interface IColumnsInfo::GetColumnInfo ou IColumnsRowset::GetColumnsRowset.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-119">The consumer can obtain the type information of each column (type, maximum length, precision, and scale) by using the IColumnsInfo::GetColumnInfo or IColumnsRowset::GetColumnsRowset interface method.</span></span> <span data-ttu-id="c7bbd-120">Em seguida, o consumidor cria um acessador para especificar as associações referentes aos dados.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-120">The consumer then creates an accessor to specify the bindings for the data.</span></span> <span data-ttu-id="c7bbd-121">A próxima etapa é inserir linhas de dados no conjunto de linhas de parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-121">The next step is to insert rows of data into the table-valued parameter rowset.</span></span> <span data-ttu-id="c7bbd-122">Isso pode ser feito usando IRowsetChange::InsertRow.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-122">This can be done by using IRowsetChange::InsertRow.</span></span> <span data-ttu-id="c7bbd-123">Se você tiver que manipular os dados, também será possível usar IRowsetChange::SetData ou IRowsetChange::DeleteRows no objeto do conjunto de linhas de parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-123">IRowsetChange::SetData or IRowsetChange::DeleteRows can also be used on the table-valued parameter rowset object if you have to manipulate the data.</span></span> <span data-ttu-id="c7bbd-124">Objetos do conjunto de linhas de parâmetro com valor de tabela são contados como referência, semelhante à transmissão de objetos.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-124">Table-valued parameter rowset objects are reference counted, similar to stream objects.</span></span>  
  
 <span data-ttu-id="c7bbd-125">Se IColumnsRowset::GetColumnsRowset for usado, haverá chamadas subsequentes para os métodos IRowset::GetNextRows, IRowset::GetData e IRowset::ReleaseRows no objeto de conjunto de linhas da coluna resultante.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-125">If IColumnsRowset::GetColumnsRowset is used, there will be subsequent calls to IRowset::GetNextRows, IRowset::GetData, and IRowset::ReleaseRows methods on the rowset object of the resulting column.</span></span>  
  
 <span data-ttu-id="c7bbd-126">Depois que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo começar a executar o comando, os valores de parâmetro com valor de tabela serão obtidos desse objeto de conjunto de linhas de parâmetro com valor de tabela e enviados ao servidor.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-126">After the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider begins executing the command, the table-valued parameter values will be fetched from this table-valued parameter rowset object and sent to the server.</span></span>  
  
 <span data-ttu-id="c7bbd-127">O modelo de push requer um esforço mínimo do consumidor, mas usa mais memória do que o modelo de pull, pois todos os dados de parâmetro com valor de tabela precisam estar na memória em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-127">The push model requires minimal work by the consumer, but uses more memory than the pull model, because all the table-valued parameter data has to be in memory at execution time.</span></span>  
  
## <a name="pull-model-obtaining-table-valued-parameter-data-on-demand-from-the-consumer"></a><span data-ttu-id="c7bbd-128">Modelo de pull (obtendo dados de parâmetro com valor de tabela sob demanda do consumidor)</span><span class="sxs-lookup"><span data-stu-id="c7bbd-128">Pull Model (Obtaining Table-Valued Parameter Data on Demand from the Consumer)</span></span>  
 <span data-ttu-id="c7bbd-129">O modelo de pull é útil para dois cenários:</span><span class="sxs-lookup"><span data-stu-id="c7bbd-129">The pull model is useful for two scenarios:</span></span>  
  
-   <span data-ttu-id="c7bbd-130">Para transmitir linhas.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-130">To stream rows.</span></span>  
  
-   <span data-ttu-id="c7bbd-131">Se um conjunto de linhas de outro provedor estiver sendo usado como o valor do parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-131">If a rowset from another provider is being used as the table-valued parameter value.</span></span>  
  
 <span data-ttu-id="c7bbd-132">No modelo de pull, o consumidor fornece dados sob demanda para o provedor.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-132">In the pull model, the consumer provides data on demand to the provider.</span></span> <span data-ttu-id="c7bbd-133">Use esta abordagem se seu aplicativo tiver muitas inserções de dados, e os dados do conjunto de linhas de parâmetro com valor de tabela na memória resultarem em acesso de memória excessivo.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-133">Use this approach if your application has many data insertions, and table-valued parameter rowset data in memory would result in excessive memory access.</span></span> <span data-ttu-id="c7bbd-134">Se forem usados vários provedores OLE DB, o modelo de pull do consumidor permitirá que o consumidor forneça qualquer objeto do conjunto de linhas como o valor de parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-134">If multiple OLE DB providers are used, the consumer pull model enables the consumer to provide any rowset object as the table-valued parameter value.</span></span>  
  
 <span data-ttu-id="c7bbd-135">Para usar o modelo de pull, os consumidores precisam fornecer suas próprias implementações de um objeto do conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-135">To use the pull model, consumers have to provide their own implementation of a rowset object.</span></span> <span data-ttu-id="c7bbd-136">Ao usar o modelo de pull com conjuntos de linhas de parâmetro com valor de tabela (CLSID_ROWSET_TVP), solicita-se que o consumidor agregue o objeto do conjunto de linhas de parâmetro com valor de tabela que o provedor expõe pelo método ITableDefinitionWithConstraints::CreateTableWithConstraints method ou pelo método IOpenRowset::OpenRowset.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-136">When using the pull model with table-valued parameter rowsets (CLSID_ROWSET_TVP), the consumer is required to aggregate the table-valued parameter rowset object that the provider exposes through the ITableDefinitionWithConstraints::CreateTableWithConstraints method or the IOpenRowset::OpenRowset method.</span></span> <span data-ttu-id="c7bbd-137">Espera-se que o objeto do consumidor substitua a implementação da interface IRowset.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-137">The consumer object is only expected to override the IRowset interface implementation.</span></span> <span data-ttu-id="c7bbd-138">Você deve substituir as seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="c7bbd-138">You must override the following functions:</span></span>  
  
-   <span data-ttu-id="c7bbd-139">IRowset::GetNextRows</span><span class="sxs-lookup"><span data-stu-id="c7bbd-139">IRowset::GetNextRows</span></span>  
  
-   <span data-ttu-id="c7bbd-140">IRowset::AddRefRows</span><span class="sxs-lookup"><span data-stu-id="c7bbd-140">IRowset::AddRefRows</span></span>  
  
-   <span data-ttu-id="c7bbd-141">IRowset::GetData</span><span class="sxs-lookup"><span data-stu-id="c7bbd-141">IRowset::GetData</span></span>  
  
-   <span data-ttu-id="c7bbd-142">IRowset::ReleaseRows</span><span class="sxs-lookup"><span data-stu-id="c7bbd-142">IRowset::ReleaseRows</span></span>  
  
-   <span data-ttu-id="c7bbd-143">IRowset::RestartPosition</span><span class="sxs-lookup"><span data-stu-id="c7bbd-143">IRowset::RestartPosition</span></span>  
  
 <span data-ttu-id="c7bbd-144">O provedor OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client lerá uma ou mais linhas no momento a partir do qual o objeto do conjunto de linhas do consumidor dará suporte ao comportamento de streaming nos parâmetros com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-144">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider will read one or more rows at a time from the consumer rowset object to support streaming behavior in table-valued parameters.</span></span> <span data-ttu-id="c7bbd-145">Por exemplo, o usuário pode ter os dados do conjunto de linhas de parâmetro com valor de tabela no disco (não na memória) e pode implementar a funcionalidade para ler dados do disco em caso de exigência do provedor OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-145">For example, the user might have the table-valued parameter rowset data on disk (not in memory) and might implement the functionality to read data from the disk when required by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider.</span></span>  
  
 <span data-ttu-id="c7bbd-146">O consumidor comunicará seu formato de dados ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo usando IAccessor:: Createaccesser no objeto conjunto de linhas de parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-146">The consumer will communicate its data format to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider by using IAccessor::CreateAccessor on the table-valued parameter rowset object.</span></span> <span data-ttu-id="c7bbd-147">Ao ler dados do buffer do consumidor, o provedor verifica se todas as colunas graváveis e não padrão estão disponíveis através de pelo menos um identificador do acessador e usa os identificadores correspondentes para ler dados das colunas.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-147">When reading data from the consumer buffer, the provider verifies that all the writable and non-default columns are available through at least one accessor handle, and uses the corresponding handles to read columns data.</span></span> <span data-ttu-id="c7bbd-148">Para evitar ambiguidade, deve haver uma correspondência um-para-um entre uma coluna do conjunto de linhas de parâmetro com valor de tabela e uma associação.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-148">To avoid ambiguity, there should be a one-to-one correspondence between a table-valued parameter rowset column and a binding.</span></span> <span data-ttu-id="c7bbd-149">Associações duplicadas para a mesma coluna resultarão em um erro.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-149">Duplicate bindings to the same column will result in an error.</span></span> <span data-ttu-id="c7bbd-150">Além disso, espera-se que cada acessador tenha o membro *iOrdinal* de DBBindings em sequência.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-150">Also, each accessor is expected to have the *iOrdinal* member of DBBindings in sequence.</span></span> <span data-ttu-id="c7bbd-151">Haverá mais chamadas a IRowset::GetData que o número de acessadores por linha, e a ordem das chamadas será baseada na ordem do valor de *iOrdinal*, dos valores mais baixos até os mais altos.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-151">There will be as many calls to IRowset::GetData as the number of accessors per row, and the order of calls will be based on the order of *iOrdinal* value from lower to higher values.</span></span>  
  
 <span data-ttu-id="c7bbd-152">É esperado que o provedor implemente a maioria das interfaces exposta pelo objeto do conjunto de linhas de parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-152">The provider is expected to implement most of the interfaces exposed by the table-valued parameter rowset object.</span></span> <span data-ttu-id="c7bbd-153">O consumidor implementará um objeto de conjunto de linhas com interfaces mínimas (IRowset).</span><span class="sxs-lookup"><span data-stu-id="c7bbd-153">The consumer will implement a rowset object with minimal interfaces (IRowset).</span></span> <span data-ttu-id="c7bbd-154">Por causa de agregação cega, as interfaces obrigatórias restantes do objeto de conjunto de linhas serão implementadas pelo objeto do conjunto de linhas de parâmetro com valor de tabela.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-154">Because of blind aggregation, the remaining mandatory rowset object interfaces will be implemented by the table-valued parameter rowset object.</span></span>  
  
 <span data-ttu-id="c7bbd-155">Para qualquer outro objeto do conjunto de linhas, como os objetos obtidos para qualquer provedor OLE DB, o conjunto de linhas fornecido pelo consumidor deverá implementar todas as interfaces obrigatórias do objeto de conjunto de linhas, conforme indicado na especificação do OLE DB.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-155">For any other rowset object, such as rowset objects obtained for any OLE DB provider, the consumer-provided rowset must implement all the mandatory rowset object interfaces as specified in the OLE DB specification.</span></span>  
  
 <span data-ttu-id="c7bbd-156">No momento da execução, o provedor OLE DB do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client chamará novamente o objeto do conjunto de linhas para buscar linhas e ler dados das colunas.</span><span class="sxs-lookup"><span data-stu-id="c7bbd-156">At the time of execution, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider will call back to the rowset object to fetch rows and read column data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7bbd-157">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c7bbd-157">See Also</span></span>  
 <span data-ttu-id="c7bbd-158">[Os parâmetros com valor de tabela &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="c7bbd-158">[Table-Valued Parameters &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span></span>  
 [<span data-ttu-id="c7bbd-159">Usar parâmetros com valor de tabela &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="c7bbd-159">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  