---
title: Caixa de diálogo Editor de transformação de limpeza DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssdqs.designer.cleansing.f1
- SQL12.SSDQS.DESIGNER.DQCONNECTION.F1
ms.assetid: 07e79641-71ee-45d0-a9ba-ed6f9f68f333
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e97cd138bb17ce3cfe476496e5bc576875728224
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569568"
---
# <a name="dqs-cleansing-transformation-editor-dialog-box"></a><span data-ttu-id="db009-102">Caixa de diálogo Editor de Transformação de Limpeza DQS</span><span class="sxs-lookup"><span data-stu-id="db009-102">DQS Cleansing Transformation Editor Dialog Box</span></span>
  <span data-ttu-id="db009-103">Use a caixa de diálogo **Editor de Transformação de Limpeza DQS** para corrigir os dados usando Data Quality Services (DQS).</span><span class="sxs-lookup"><span data-stu-id="db009-103">Use the **DQS Cleansing Transformation Editor** dialog box to correct data using Data Quality Services (DQS).</span></span> <span data-ttu-id="db009-104">Para obter mais informações, consulte [Data Quality Services Concepts](../../2014/data-quality-services/data-quality-services-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="db009-104">For more information, see [Data Quality Services Concepts](../../2014/data-quality-services/data-quality-services-concepts.md).</span></span>  
  
 <span data-ttu-id="db009-105">Para saber mais sobre a transformação, consulte [DQS Cleansing Transformation](data-flow/transformations/dqs-cleansing-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="db009-105">To learn more about the transformation, see [DQS Cleansing Transformation](data-flow/transformations/dqs-cleansing-transformation.md).</span></span>  
  
 <span data-ttu-id="db009-106">**O que você deseja fazer?**</span><span class="sxs-lookup"><span data-stu-id="db009-106">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="db009-107">Abrir o editor de transformação de limpeza DQS</span><span class="sxs-lookup"><span data-stu-id="db009-107">Open the DQS Cleansing Transformation Editor</span></span>](#open)  
  
-   [<span data-ttu-id="db009-108">Definir as opções na guia de Gerenciador de Conexões</span><span class="sxs-lookup"><span data-stu-id="db009-108">Set options on the Connection Manager tab</span></span>](#connection)  
  
-   [<span data-ttu-id="db009-109">Definir as opções na guia Mapeamento</span><span class="sxs-lookup"><span data-stu-id="db009-109">Set options on the Mapping tab</span></span>](#mapping)  
  
-   [<span data-ttu-id="db009-110">Definir as opções na guia Avançado</span><span class="sxs-lookup"><span data-stu-id="db009-110">Set options on the Advanced tab</span></span>](#advanced)  
  
-   [<span data-ttu-id="db009-111">Definir as opções na caixa de diálogo Gerenciador de conexões de limpeza DQS</span><span class="sxs-lookup"><span data-stu-id="db009-111">Set the options in the DQS Cleansing Connection Manager dialog box</span></span>](#manager)  
  
##  <a name="open-the-dqs-cleansing-transformation-editor"></a><a name="open"></a> <span data-ttu-id="db009-112">Abra o Editor de Transformação de Limpeza DQS.</span><span class="sxs-lookup"><span data-stu-id="db009-112">Open the DQS Cleansing Transformation Editor</span></span>  
  
1.  <span data-ttu-id="db009-113">Adicione a Transformação de Limpeza DQS ao pacote do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="db009-113">Add the DQS Cleansing Transformation to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="db009-114">Clique com o botão direito do mouse no componente e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="db009-114">Right-click the component and then click **Edit**.</span></span>  
  
##  <a name="set-options-on-the-connection-manager-tab"></a><a name="connection"></a><span data-ttu-id="db009-115">Definir opções na guia Gerenciador de conexões</span><span class="sxs-lookup"><span data-stu-id="db009-115">Set options on the Connection Manager tab</span></span>  
 <span data-ttu-id="db009-116">**Gerenciador de conexões de qualidade de dados**</span><span class="sxs-lookup"><span data-stu-id="db009-116">**Data quality connection manager**</span></span>  
 <span data-ttu-id="db009-117">Selecione um gerenciador de conexões DQS existente na lista ou crie uma nova conexão clicando em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="db009-117">Select an existing DQS connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="db009-118">**Novo**</span><span class="sxs-lookup"><span data-stu-id="db009-118">**New**</span></span>  
 <span data-ttu-id="db009-119">Crie um novo gerenciador de conexões, usando a caixa de diálogo **Gerenciador de Conexões de Limpeza DQS** .</span><span class="sxs-lookup"><span data-stu-id="db009-119">Create a new connection manager by using the **DQS Cleansing Connection Manager** dialog box.</span></span> <span data-ttu-id="db009-120">Consulte [definir as opções na caixa de diálogo Gerenciador de conexões de limpeza DQS](#manager)</span><span class="sxs-lookup"><span data-stu-id="db009-120">See [Set the options in the DQS Cleansing Connection Manager dialog box](#manager)</span></span>  
  
 <span data-ttu-id="db009-121">**Base de conhecimento de qualidade de dados**</span><span class="sxs-lookup"><span data-stu-id="db009-121">**Data Quality Knowledge Base**</span></span>  
 <span data-ttu-id="db009-122">Selecione uma base de dados de conhecimento do DQS para a fonte de dados conectada.</span><span class="sxs-lookup"><span data-stu-id="db009-122">Select an existing DQS knowledge base for the connected data source.</span></span> <span data-ttu-id="db009-123">Para obter mais informações sobre a base de dados de conhecimento do DQS, consulte [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="db009-123">For more information about the DQS knowledge base, see [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span>  
  
 <span data-ttu-id="db009-124">**Criptografar a conexão**</span><span class="sxs-lookup"><span data-stu-id="db009-124">**Encrypt connection**</span></span>  
 <span data-ttu-id="db009-125">Especifique se deseja criptografar a conexão, a fim de criptografar a transferência de dados entre o servidor DQS e o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="db009-125">specify whether to encrypt the connection, in order to encrypt the data transfer between the DQS Server and [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="db009-126">**Domínios disponíveis**</span><span class="sxs-lookup"><span data-stu-id="db009-126">**Available domains**</span></span>  
 <span data-ttu-id="db009-127">Liste os domínios disponíveis para a base de conhecimento selecionada.</span><span class="sxs-lookup"><span data-stu-id="db009-127">Lists the available domains for the selected knowledge base.</span></span> <span data-ttu-id="db009-128">Há dois tipos de domínios: domínios únicos e domínios compostos que contêm dois ou mais domínios únicos.</span><span class="sxs-lookup"><span data-stu-id="db009-128">There are two types of domains: single domains, and composite domains that contain two or more single domains.</span></span>  
  
 <span data-ttu-id="db009-129">Para obter mais informações sobre como mapear colunas para domínios compostos, consulte [Map Columns to Composite Domains](data-flow/transformations/map-columns-to-composite-domains.md).</span><span class="sxs-lookup"><span data-stu-id="db009-129">For information on how to map columns to composite domains, see [Map Columns to Composite Domains](data-flow/transformations/map-columns-to-composite-domains.md).</span></span>  
  
 <span data-ttu-id="db009-130">Para obter mais informações sobre domínios, consulte [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="db009-130">For more information about domains, see [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span>  
  
 <span data-ttu-id="db009-131">**Configurar Saída de Erro**</span><span class="sxs-lookup"><span data-stu-id="db009-131">**Configure Error Output**</span></span>  
 <span data-ttu-id="db009-132">Especifique como tratar erros em nível de linha.</span><span class="sxs-lookup"><span data-stu-id="db009-132">Specify how to handle row-level errors.</span></span> <span data-ttu-id="db009-133">Podem ocorrer erros quando a transformação corrige dados da fonte de dados conectada, devido a valores de dados inesperados ou restrições de validação.</span><span class="sxs-lookup"><span data-stu-id="db009-133">Errors can occur when the transformation corrects data from the connected data source, due to unexpected data values or validation constraints.</span></span>  
  
 <span data-ttu-id="db009-134">Os valores válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="db009-134">The following are the valid values:</span></span>  
  
-   <span data-ttu-id="db009-135">**Falha no Componente**, que indica que houve falha na transformação e os dados de entrada não são inseridos no banco de dados do Data Quality Services.</span><span class="sxs-lookup"><span data-stu-id="db009-135">**Fail Component**, which indicates that the transformation fails and the input data is not inserted into the Data Quality Services database.</span></span> <span data-ttu-id="db009-136">Este é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="db009-136">This is the default value.</span></span>  
  
-   <span data-ttu-id="db009-137">**Redirecionar Linha**, que indica que os dados de entrada não estão inseridos no banco de dados do Data Quality Services e são redirecionados para a saída do erro.</span><span class="sxs-lookup"><span data-stu-id="db009-137">**Redirect Row**, which indicates that the input data is not inserted into the Data Quality Services database and is redirected to the error output.</span></span>  
  
##  <a name="set-options-on-the-mapping-tab"></a><a name="mapping"></a><span data-ttu-id="db009-138">Definir opções na guia mapeamento</span><span class="sxs-lookup"><span data-stu-id="db009-138">Set options on the Mapping tab</span></span>  
 <span data-ttu-id="db009-139">Para obter mais informações sobre como mapear colunas para domínios compostos, consulte [Map Columns to Composite Domains](data-flow/transformations/map-columns-to-composite-domains.md).</span><span class="sxs-lookup"><span data-stu-id="db009-139">For information on how to map columns to composite domains, see [Map Columns to Composite Domains](data-flow/transformations/map-columns-to-composite-domains.md).</span></span>  
  
 <span data-ttu-id="db009-140">**Colunas de Entrada Disponíveis**</span><span class="sxs-lookup"><span data-stu-id="db009-140">**Available Input Columns**</span></span>  
 <span data-ttu-id="db009-141">Lista as colunas da fonte de dados conectada.</span><span class="sxs-lookup"><span data-stu-id="db009-141">Lists the columns from the connected data source.</span></span> <span data-ttu-id="db009-142">Selecione uma ou mais colunas que contêm os dados que você quer corrigir.</span><span class="sxs-lookup"><span data-stu-id="db009-142">Select one or more columns that contain data that you want to correct.</span></span>  
  
 <span data-ttu-id="db009-143">**Coluna de Entrada**</span><span class="sxs-lookup"><span data-stu-id="db009-143">**Input Column**</span></span>  
 <span data-ttu-id="db009-144">Lista uma coluna de entrada que você selecionou na área **Colunas de Entrada Disponíveis** .</span><span class="sxs-lookup"><span data-stu-id="db009-144">Lists an input column that you selected in the **Available Input Columns** area.</span></span>  
  
 <span data-ttu-id="db009-145">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="db009-145">**Domain**</span></span>  
 <span data-ttu-id="db009-146">Selecione um domínio para mapear para a coluna de entrada.</span><span class="sxs-lookup"><span data-stu-id="db009-146">Select a domain to map to the input column.</span></span>  
  
 <span data-ttu-id="db009-147">**Alias de origem**</span><span class="sxs-lookup"><span data-stu-id="db009-147">**Source Alias**</span></span>  
 <span data-ttu-id="db009-148">Lista a coluna de origem que contém o valor de coluna original.</span><span class="sxs-lookup"><span data-stu-id="db009-148">Lists the source column that contains the original column value.</span></span>  
  
 <span data-ttu-id="db009-149">Clique no campo para modificar o nome da coluna.</span><span class="sxs-lookup"><span data-stu-id="db009-149">Click in the field to modify the column name.</span></span>  
  
 <span data-ttu-id="db009-150">**Alias de Saída**</span><span class="sxs-lookup"><span data-stu-id="db009-150">**Output Alias**</span></span>  
 <span data-ttu-id="db009-151">Lista a coluna que é enviada pela **Transformação de Limpeza DQS**.</span><span class="sxs-lookup"><span data-stu-id="db009-151">Lists the column that is outputted by the **DQS Cleansing Transformation**.</span></span> <span data-ttu-id="db009-152">A coluna contém o valor de coluna original ou o valor corrigido.</span><span class="sxs-lookup"><span data-stu-id="db009-152">The column contains the original column value or the corrected value.</span></span>  
  
 <span data-ttu-id="db009-153">Clique no campo para modificar o nome da coluna.</span><span class="sxs-lookup"><span data-stu-id="db009-153">Click in the field to modify the column name.</span></span>  
  
 <span data-ttu-id="db009-154">**Alias de status**</span><span class="sxs-lookup"><span data-stu-id="db009-154">**Status Alias**</span></span>  
 <span data-ttu-id="db009-155">Lista a coluna que contém informações de status para os dados corrigidos.</span><span class="sxs-lookup"><span data-stu-id="db009-155">Lists the column that contains status information for the corrected data.</span></span> <span data-ttu-id="db009-156">Clique no campo para modificar o nome da coluna.</span><span class="sxs-lookup"><span data-stu-id="db009-156">Click in the field to modify the column name.</span></span>  
  
##  <a name="set-options-on-the-advanced-tab"></a><a name="advanced"></a><span data-ttu-id="db009-157">Definir opções na guia Avançado</span><span class="sxs-lookup"><span data-stu-id="db009-157">Set options on the Advanced tab</span></span>  
 <span data-ttu-id="db009-158">**Padronizar saída**</span><span class="sxs-lookup"><span data-stu-id="db009-158">**Standardize output**</span></span>  
 <span data-ttu-id="db009-159">Indique se é preciso produzir os dados no formato padronizado com base no formato de saída definido para domínios.</span><span class="sxs-lookup"><span data-stu-id="db009-159">Indicate whether to output the data in the standardized format based on the output format defined for domains.</span></span> <span data-ttu-id="db009-160">Para obter mais informações sobre o formato padronizado, consulte [Limpeza de dados](../../2014/data-quality-services/data-cleansing.md).</span><span class="sxs-lookup"><span data-stu-id="db009-160">For more information about standardized format, see [Data Cleansing](../../2014/data-quality-services/data-cleansing.md).</span></span>  
  
 <span data-ttu-id="db009-161">**Confiança**</span><span class="sxs-lookup"><span data-stu-id="db009-161">**Confidence**</span></span>  
 <span data-ttu-id="db009-162">Indique se é preciso incluir o nível de confiança para os dados corrigidos.</span><span class="sxs-lookup"><span data-stu-id="db009-162">Indicate whether to include the confidence level for corrected data.</span></span> <span data-ttu-id="db009-163">O nível de confiança indica a extensão de certeza do DQS para a correção ou sugestão.</span><span class="sxs-lookup"><span data-stu-id="db009-163">The confidence level indicates the extend of certainty of DQS for the correction or suggestion.</span></span> <span data-ttu-id="db009-164">Para obter mais informações sobre níveis de confiança, consulte [Limpeza de dados](../../2014/data-quality-services/data-cleansing.md).</span><span class="sxs-lookup"><span data-stu-id="db009-164">For more information about confidence levels, see [Data Cleansing](../../2014/data-quality-services/data-cleansing.md).</span></span>  
  
 <span data-ttu-id="db009-165">**Motivo**</span><span class="sxs-lookup"><span data-stu-id="db009-165">**Reason**</span></span>  
 <span data-ttu-id="db009-166">Indique se é preciso incluir a razão para a correção de dados.</span><span class="sxs-lookup"><span data-stu-id="db009-166">Indicate whether to include the reason for the data correction.</span></span>  
  
 <span data-ttu-id="db009-167">**Dados acrescentados**</span><span class="sxs-lookup"><span data-stu-id="db009-167">**Appended Data**</span></span>  
 <span data-ttu-id="db009-168">Indique se é preciso produzir dados adicionais que são recebidos de um provedor de dados de referência existente.</span><span class="sxs-lookup"><span data-stu-id="db009-168">Indicate whether to output additional data that is received from an existing reference data provider.</span></span> <span data-ttu-id="db009-169">Para obter mais informações, consulte [Reference Data Services in DQS](../../2014/data-quality-services/reference-data-services-in-dqs.md).</span><span class="sxs-lookup"><span data-stu-id="db009-169">For more information, see [Reference Data Services in DQS](../../2014/data-quality-services/reference-data-services-in-dqs.md).</span></span>  
  
 <span data-ttu-id="db009-170">**Esquema de dados acrescentado**</span><span class="sxs-lookup"><span data-stu-id="db009-170">**Appended Data Schema**</span></span>  
 <span data-ttu-id="db009-171">Indique se é preciso produzir o esquema de dados.</span><span class="sxs-lookup"><span data-stu-id="db009-171">Indicate whether to output the data schema.</span></span> <span data-ttu-id="db009-172">Para obter mais informações, consulte [anexar um domínio ou domínio de composição aos dados de referência](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span><span class="sxs-lookup"><span data-stu-id="db009-172">For more information, see [Attach a Domain or Composite Domain to Reference Data](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span></span>  
  
##  <a name="set-the-options-in-the-dqs-cleansing-connection-manager-dialog-box"></a><a name="manager"></a><span data-ttu-id="db009-173">Definir as opções na caixa de diálogo Gerenciador de conexões de limpeza DQS</span><span class="sxs-lookup"><span data-stu-id="db009-173">Set the options in the DQS Cleansing Connection Manager dialog box</span></span>  
 <span data-ttu-id="db009-174">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="db009-174">**Server name**</span></span>  
 <span data-ttu-id="db009-175">Selecione ou digite o nome do servidor DQS ao qual você deseja se conectar.</span><span class="sxs-lookup"><span data-stu-id="db009-175">Select or type the name of the DQS server that you want to connect to.</span></span> <span data-ttu-id="db009-176">Para obter mais informações sobre o servidor, consulte [DQS Administration](../../2014/data-quality-services/dqs-administration.md).</span><span class="sxs-lookup"><span data-stu-id="db009-176">For more information about the server, see [DQS Administration](../../2014/data-quality-services/dqs-administration.md).</span></span>  
  
 <span data-ttu-id="db009-177">**Testar Conexão**</span><span class="sxs-lookup"><span data-stu-id="db009-177">**Test Connection**</span></span>  
 <span data-ttu-id="db009-178">Clique para confirmar se a conexão especificada é viável.</span><span class="sxs-lookup"><span data-stu-id="db009-178">Click to confirm that the connection that you specified is viable.</span></span>  
  
 <span data-ttu-id="db009-179">Você também pode abrir a caixa de diálogo **Gerenciador de Conexões de Limpeza DQS** da área de conexões, fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="db009-179">You can also open the **DQS Cleansing Connection Manager** dialog box from the connections area, by doing the following:</span></span>  
  
1.  <span data-ttu-id="db009-180">No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra um projeto existente do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ou crie um novo projeto.</span><span class="sxs-lookup"><span data-stu-id="db009-180">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open an existing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project or create a new one.</span></span>  
  
2.  <span data-ttu-id="db009-181">Clique com o botão direito do mouse na área de conexões, clique em **Nova Conexão**e, em seguida, clique em **DQS**.</span><span class="sxs-lookup"><span data-stu-id="db009-181">Right-click in the connections area, click **New Connection**, and then click **DQS**.</span></span>  
  
3.  <span data-ttu-id="db009-182">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="db009-182">Click **Add**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db009-183">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="db009-183">See Also</span></span>  
 [<span data-ttu-id="db009-184">Aplicar regras de qualidade de dados à fonte de dados</span><span class="sxs-lookup"><span data-stu-id="db009-184">Apply Data Quality Rules to Data Source</span></span>](data-flow/transformations/apply-data-quality-rules-to-data-source.md)  
  
  
