---
title: Criar Novo InfoObject | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3587a633-1c0b-4d63-a22a-6b2b93923c3a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 022f2d1e3fe10ae037ea379a02a18845b3a36107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582560"
---
# <a name="create-new-infoobject"></a><span data-ttu-id="b3332-102">Criar Novo InfoObject</span><span class="sxs-lookup"><span data-stu-id="b3332-102">Create New InfoObject</span></span>
  <span data-ttu-id="b3332-103">Use a caixa de diálogo **Criar Novo InfoObject** para criar um novo InfoObject no sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="b3332-103">Use the **Create New InfoObject** dialog box to create a new InfoObject in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="b3332-104">Você pode abrir a caixa de diálogo **Criar InfoObject** da página **Gerenciador de Conexões** do **Editor de Destino SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="b3332-104">You can open the **Create InfoObject** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="b3332-105">Para obter mais informações sobre o destino SAP BW, consulte [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="b3332-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b3332-106">A documentação do Microsoft Connector 1.1 for SAP BW supõe familiaridade com o ambiente do SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="b3332-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="b3332-107">Para obter mais informações sobre o SAP Netweaver BW ou para obter informações sobre como configurar objetos e processos do SAP Netweaver BW, consulte sua documentação do SAP.</span><span class="sxs-lookup"><span data-stu-id="b3332-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="b3332-108">**Para abrir a caixa de diálogo Criar Novo InfoObject**</span><span class="sxs-lookup"><span data-stu-id="b3332-108">**To open the Create New InfoObject dialog box**</span></span>  
  
1.  <span data-ttu-id="b3332-109">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="b3332-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="b3332-110">Na guia **Fluxo de Dados** , clique duas vezes no destino SAP BW.</span><span class="sxs-lookup"><span data-stu-id="b3332-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="b3332-111">No **Editor de Destino SAP BW**, clique em **Gerenciador de Conexões** para abrir a página **Gerenciador de Conexões** do editor.</span><span class="sxs-lookup"><span data-stu-id="b3332-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="b3332-112">Na página **Gerenciador de Conexões** , na caixa do grupo **Criar Objetos SAP BW** , execute uma destas etapas para criar um InfoObject:</span><span class="sxs-lookup"><span data-stu-id="b3332-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, do one of the following steps to create an InfoObject:</span></span>  
  
    1.  <span data-ttu-id="b3332-113">Para criar um InfoObject diretamente, selecione **InfoObject**e clique em **Criar** para abrir a caixa de diálogo **Criar Novo InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="b3332-113">To create an InfoObject directly, select **InfoObject**, and then click **Create** to open the **Create New InfoObject** dialog box.</span></span>  
  
    2.  <span data-ttu-id="b3332-114">Para criar um InfoObject ao criar um InfoCube, selecione **InfoCube**e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="b3332-114">To create an InfoObject while creating an InfoCube, select **InfoCube**, and then click **Create**.</span></span> <span data-ttu-id="b3332-115">Na caixa de diálogo **Criar InfoCube para os Dados da Transação** , na coluna **IObject** de uma das linhas na lista, selecione **Criar** para abrir a caixa de diálogo **Criar Novo InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="b3332-115">In the **Create InfoCube for Transaction Data** dialog box, in the **IObject** column for one of the rows in the list, select **Create** to open the **Create New InfoObject** dialog box.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="b3332-116">Cada linha na tabela representa uma coluna no fluxo de dados do pacote.</span><span class="sxs-lookup"><span data-stu-id="b3332-116">Each row in the table represents a column in the data flow of the package.</span></span>  
  
    3.  <span data-ttu-id="b3332-117">Para criar um InfoObject ao criar um InfoSource para dados transacionais, selecione **InfoSource**e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="b3332-117">To create an InfoObject while creating an InfoSouce for transactional data, select **InfoSource**, and then click **Create**.</span></span> <span data-ttu-id="b3332-118">Na caixa de diálogo **Criar InfoSource** , selecione **Dados da Transação**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3332-118">In the **Create InfoSource** dialog box, select **Transaction Data**, and then click **OK**.</span></span> <span data-ttu-id="b3332-119">Na caixa de diálogo **Criar InfoSource para os Dados da Transação** , na coluna **IObject** de uma das linhas na lista, selecione **Criar** para abrir a caixa de diálogo **Criar Novo InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="b3332-119">In the **Create InfoSource for Transaction Data** dialog box, in the **IObject** column for one of the rows in the list, select **Create** to open the **Create New InfoObject** dialog box.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="b3332-120">Cada linha na tabela representa uma coluna no fluxo de dados do pacote.</span><span class="sxs-lookup"><span data-stu-id="b3332-120">Each row in the table represents a column in the data flow of the package.</span></span>  
  
    4.  <span data-ttu-id="b3332-121">Para criar um InfoObject ao criar um InfoSource para dados mestres, selecione **InfoSource**e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="b3332-121">To create an InfoObject while creating an InfoSource for master data, select **InfoSource**, and then click **Create**.</span></span> <span data-ttu-id="b3332-122">Na caixa de diálogo **Criar InfoSource** , selecione **Dados Mestres**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3332-122">In the **Create InfoSource** dialog box, select **Master Data**, and then click **OK**.</span></span> <span data-ttu-id="b3332-123">Na caixa de diálogo **Criar InfoSource para Dados Mestres** , clique em **Novo** para abrir a caixa de diálogo **Criar Novo InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="b3332-123">In the **Create InfoSource for Master Data** dialog box, click **New** to open the **Create New InfoObject** dialog box.</span></span>  
  
 <span data-ttu-id="b3332-124">Você também pode abrir a caixa de diálogo **Criar Novo InfoObject** clicando em **Novo** na seção **Atributos** da caixa de diálogo **Criar Novo InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="b3332-124">You can also open the **Create New InfoObject** dialog box by clicking **New** in the **Attributes** section of the **Create New InfoObject** dialog box.</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="b3332-125">Opções gerais</span><span class="sxs-lookup"><span data-stu-id="b3332-125">General Options</span></span>  
 <span data-ttu-id="b3332-126">**Característica**</span><span class="sxs-lookup"><span data-stu-id="b3332-126">**Characteristic**</span></span>  
 <span data-ttu-id="b3332-127">Crie um InfoObject que representa os dados da dimensão.</span><span class="sxs-lookup"><span data-stu-id="b3332-127">Create an InfoObject that represents dimension data.</span></span>  
  
 <span data-ttu-id="b3332-128">**Valor-chave**</span><span class="sxs-lookup"><span data-stu-id="b3332-128">**Key figure**</span></span>  
 <span data-ttu-id="b3332-129">Crie um InfoObject que representa os dados de fato.</span><span class="sxs-lookup"><span data-stu-id="b3332-129">Create an InfoObject that represents fact data.</span></span>  
  
 <span data-ttu-id="b3332-130">**Nome do InfoObject**</span><span class="sxs-lookup"><span data-stu-id="b3332-130">**InfoObject name**</span></span>  
 <span data-ttu-id="b3332-131">Digite um nome para o InfoObject.</span><span class="sxs-lookup"><span data-stu-id="b3332-131">Enter a name for the InfoObject.</span></span>  
  
 <span data-ttu-id="b3332-132">**Descrição breve**</span><span class="sxs-lookup"><span data-stu-id="b3332-132">**Short description**</span></span>  
 <span data-ttu-id="b3332-133">Insira uma descrição curta para o InfoObject.</span><span class="sxs-lookup"><span data-stu-id="b3332-133">Enter a short description for the InfoObject.</span></span>  
  
 <span data-ttu-id="b3332-134">**Descrição longa**</span><span class="sxs-lookup"><span data-stu-id="b3332-134">**Long description**</span></span>  
 <span data-ttu-id="b3332-135">Insira uma descrição longa para o InfoObject.</span><span class="sxs-lookup"><span data-stu-id="b3332-135">Enter a long description for the InfoObject.</span></span>  
  
 <span data-ttu-id="b3332-136">**Com dados mestres**</span><span class="sxs-lookup"><span data-stu-id="b3332-136">**Has master data**</span></span>  
 <span data-ttu-id="b3332-137">Indica que o InfoObject contém dados mestres na forma de atributos, textos ou hierarquias.</span><span class="sxs-lookup"><span data-stu-id="b3332-137">Indicate that the InfoObject contains master data in the form of attributes, texts, or hierarchies.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b3332-138">Selecione esta opção se o InfoObject representar dados dimensionais e você tiver selecionado a opção **Característica** .</span><span class="sxs-lookup"><span data-stu-id="b3332-138">Select this option if the InfoObject represents dimensional data and you have selected the **Characteristic** option.</span></span>  
  
 <span data-ttu-id="b3332-139">**Permitir caracteres minúsculos**</span><span class="sxs-lookup"><span data-stu-id="b3332-139">**Allow lower-case characters**</span></span>  
 <span data-ttu-id="b3332-140">Permitir caracteres minúsculos nos dados do InfoObject.</span><span class="sxs-lookup"><span data-stu-id="b3332-140">Allow lower-case characters in the InfoObject data.</span></span>  
  
 <span data-ttu-id="b3332-141">**Salvar e Ativar**</span><span class="sxs-lookup"><span data-stu-id="b3332-141">**Save & Activate**</span></span>  
 <span data-ttu-id="b3332-142">Salvar e ativar o novo InfoObject.</span><span class="sxs-lookup"><span data-stu-id="b3332-142">Save and active the new InfoObject.</span></span>  
  
## <a name="data-type-options"></a><span data-ttu-id="b3332-143">Opções de tipo de dados</span><span class="sxs-lookup"><span data-stu-id="b3332-143">Data Type Options</span></span>  
 <span data-ttu-id="b3332-144">**CHAR - Cadeia de caracteres**</span><span class="sxs-lookup"><span data-stu-id="b3332-144">**CHAR - Character String**</span></span>  
 <span data-ttu-id="b3332-145">Indica que o InfoObject contém dados de caracteres.</span><span class="sxs-lookup"><span data-stu-id="b3332-145">Indicates that the InfoObject contains character data.</span></span>  
  
 <span data-ttu-id="b3332-146">**NUMC - Cadeia de Caracteres Numéricos**</span><span class="sxs-lookup"><span data-stu-id="b3332-146">**NUMC - Numeric String**</span></span>  
 <span data-ttu-id="b3332-147">Indica que o InfoObject contém dados numéricos.</span><span class="sxs-lookup"><span data-stu-id="b3332-147">Indicates that the InfoObject contains numeric data.</span></span>  
  
 <span data-ttu-id="b3332-148">**DATS - Data (AAAAMMDD)**</span><span class="sxs-lookup"><span data-stu-id="b3332-148">**DATS - Date (YYYYMMDD)**</span></span>  
 <span data-ttu-id="b3332-149">Indica que o InfoObject contém dados de data.</span><span class="sxs-lookup"><span data-stu-id="b3332-149">Indicates that the InfoObject contains date data.</span></span>  
  
 <span data-ttu-id="b3332-150">**TIMS - Hora (HHMMSS)**</span><span class="sxs-lookup"><span data-stu-id="b3332-150">**TIMS - Time (HHMMSS)**</span></span>  
 <span data-ttu-id="b3332-151">Indica que o InfoObject contém dados de hora.</span><span class="sxs-lookup"><span data-stu-id="b3332-151">Indicates that the InfoObject contains time data.</span></span>  
  
 <span data-ttu-id="b3332-152">**Comprimento**</span><span class="sxs-lookup"><span data-stu-id="b3332-152">**Length**</span></span>  
 <span data-ttu-id="b3332-153">Insira o comprimento dos dados.</span><span class="sxs-lookup"><span data-stu-id="b3332-153">Enter the length of the data.</span></span>  
  
## <a name="text-options"></a><span data-ttu-id="b3332-154">Opções de texto</span><span class="sxs-lookup"><span data-stu-id="b3332-154">Text Options</span></span>  
 <span data-ttu-id="b3332-155">**Com textos**</span><span class="sxs-lookup"><span data-stu-id="b3332-155">**With Texts**</span></span>  
 <span data-ttu-id="b3332-156">Indica que o InfoObject contém textos.</span><span class="sxs-lookup"><span data-stu-id="b3332-156">Indicate that the InfoObject contains texts.</span></span>  
  
 <span data-ttu-id="b3332-157">**Texto curto**</span><span class="sxs-lookup"><span data-stu-id="b3332-157">**Short Text**</span></span>  
 <span data-ttu-id="b3332-158">Indica que o InfoObject contém textos curtos.</span><span class="sxs-lookup"><span data-stu-id="b3332-158">Indicates that the InfoObject contains short texts.</span></span>  
  
 <span data-ttu-id="b3332-159">**Texto médio**</span><span class="sxs-lookup"><span data-stu-id="b3332-159">**Medium Text**</span></span>  
 <span data-ttu-id="b3332-160">Indica que o InfoObject contém textos médios.</span><span class="sxs-lookup"><span data-stu-id="b3332-160">Indicates that the InfoObject contains medium texts.</span></span>  
  
 <span data-ttu-id="b3332-161">**Texto longo**</span><span class="sxs-lookup"><span data-stu-id="b3332-161">**Long Text**</span></span>  
 <span data-ttu-id="b3332-162">Indica que o InfoObject contém textos longos.</span><span class="sxs-lookup"><span data-stu-id="b3332-162">Indicates that the InfoObject contains long texts.</span></span>  
  
 <span data-ttu-id="b3332-163">**Dependente do idioma do texto**</span><span class="sxs-lookup"><span data-stu-id="b3332-163">**Text Language-Dependent**</span></span>  
 <span data-ttu-id="b3332-164">Indica que os textos dependem da linguagem.</span><span class="sxs-lookup"><span data-stu-id="b3332-164">Indicates that the texts are language-dependent.</span></span>  
  
 <span data-ttu-id="b3332-165">**Dependente da hora do texto**</span><span class="sxs-lookup"><span data-stu-id="b3332-165">**Text Time-Dependent**</span></span>  
 <span data-ttu-id="b3332-166">Indica que os textos dependem da hora.</span><span class="sxs-lookup"><span data-stu-id="b3332-166">Indicates that the texts are time-dependent.</span></span>  
  
## <a name="attributes-section"></a><span data-ttu-id="b3332-167">Seção de atributos</span><span class="sxs-lookup"><span data-stu-id="b3332-167">Attributes Section</span></span>  
 <span data-ttu-id="b3332-168">A seção **Atributos** consiste em uma lista de atributos para o InfoObject e as opções que permitem adicionar e remover atributos da lista.</span><span class="sxs-lookup"><span data-stu-id="b3332-168">The **Attributes** section consists of a list of attributes for the InfoObject, and the options that let you add and remove attributes from the list.</span></span>  
  
### <a name="attributes-list"></a><span data-ttu-id="b3332-169">Lista de atributos</span><span class="sxs-lookup"><span data-stu-id="b3332-169">Attributes List</span></span>  
 <span data-ttu-id="b3332-170">A lista **Atributos** exibe os atributos do InfoObject que você está criando.</span><span class="sxs-lookup"><span data-stu-id="b3332-170">The **Attributes** list displays the attributes of the InfoObject that you are creating.</span></span> <span data-ttu-id="b3332-171">A lista **Atributos** tem os seguintes cabeçalhos de coluna:</span><span class="sxs-lookup"><span data-stu-id="b3332-171">The **Attributes** list has the following column headings:</span></span>  
  
 <span data-ttu-id="b3332-172">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="b3332-172">**InfoObject**</span></span>  
 <span data-ttu-id="b3332-173">Exiba o nome do InfoObject.</span><span class="sxs-lookup"><span data-stu-id="b3332-173">View the name of the InfoObject.</span></span>  
  
 <span data-ttu-id="b3332-174">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b3332-174">**Description**</span></span>  
 <span data-ttu-id="b3332-175">Visualize a descrição do InfoObject.</span><span class="sxs-lookup"><span data-stu-id="b3332-175">View the description of the InfoObject.</span></span>  
  
 <span data-ttu-id="b3332-176">**Tipo do InfoObject**</span><span class="sxs-lookup"><span data-stu-id="b3332-176">**InfoObject Type**</span></span>  
 <span data-ttu-id="b3332-177">Exiba o tipo do InfoObject.</span><span class="sxs-lookup"><span data-stu-id="b3332-177">View the type of the InfoObject.</span></span> <span data-ttu-id="b3332-178">A tabela a seguir lista os valores possíveis do tipo.</span><span class="sxs-lookup"><span data-stu-id="b3332-178">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="b3332-179">Valor</span><span class="sxs-lookup"><span data-stu-id="b3332-179">Value</span></span>|<span data-ttu-id="b3332-180">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="b3332-180">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b3332-181">CHA</span><span class="sxs-lookup"><span data-stu-id="b3332-181">CHA</span></span>|<span data-ttu-id="b3332-182">Características</span><span class="sxs-lookup"><span data-stu-id="b3332-182">Characteristics</span></span>|  
|<span data-ttu-id="b3332-183">KYF</span><span class="sxs-lookup"><span data-stu-id="b3332-183">KYF</span></span>|<span data-ttu-id="b3332-184">Valores-chave</span><span class="sxs-lookup"><span data-stu-id="b3332-184">Key figures</span></span>|  
|<span data-ttu-id="b3332-185">UNI</span><span class="sxs-lookup"><span data-stu-id="b3332-185">UNI</span></span>|<span data-ttu-id="b3332-186">Unidades</span><span class="sxs-lookup"><span data-stu-id="b3332-186">Units</span></span>|  
|<span data-ttu-id="b3332-187">TIM</span><span class="sxs-lookup"><span data-stu-id="b3332-187">TIM</span></span>|<span data-ttu-id="b3332-188">Características de hora</span><span class="sxs-lookup"><span data-stu-id="b3332-188">Time characteristics</span></span>|  
  
### <a name="attributes-options"></a><span data-ttu-id="b3332-189">Opções do atributo</span><span class="sxs-lookup"><span data-stu-id="b3332-189">Attributes Options</span></span>  
 <span data-ttu-id="b3332-190">Use as opções a seguir para adicionar e remover atributos para o InfoObject que você está criando:</span><span class="sxs-lookup"><span data-stu-id="b3332-190">Use the following options to add and remove attributes for the InfoObject that you are creating:</span></span>  
  
 <span data-ttu-id="b3332-191">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="b3332-191">**Add**</span></span>  
 <span data-ttu-id="b3332-192">Adicione um InfoObject existente como um atributo.</span><span class="sxs-lookup"><span data-stu-id="b3332-192">Add an existing InfoObject as an attribute.</span></span>  
  
 <span data-ttu-id="b3332-193">Para adicionar um InfoObject existente, clique em Adicionar e use a caixa de diálogo **Pesquisar InfoObject** para localizar o InfoObject.</span><span class="sxs-lookup"><span data-stu-id="b3332-193">To add an existing InfoObject, click Add, and then use the **Look Up InfoObject** dialog box to find the InfoObject.</span></span> <span data-ttu-id="b3332-194">Para obter mais informações sobre essa caixa de diálogo, consulte [Look Up InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="b3332-194">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="b3332-195">**Novo**</span><span class="sxs-lookup"><span data-stu-id="b3332-195">**New**</span></span>  
 <span data-ttu-id="b3332-196">Adicione um novo InfoObject como um atributo.</span><span class="sxs-lookup"><span data-stu-id="b3332-196">Add a new InfoObject as an attribute.</span></span>  
  
 <span data-ttu-id="b3332-197">Para criar e adicionar um novo InfoObject, clique em Novo e use uma nova instância da caixa de diálogo **Criar Novo InfoObject** para criar o novo InfoObject.</span><span class="sxs-lookup"><span data-stu-id="b3332-197">To create and add a new InfoObject, click New, and then use a new instance of the **Create New InfoObject** dialog box to create the new InfoObject.</span></span>  
  
 <span data-ttu-id="b3332-198">**Remover**</span><span class="sxs-lookup"><span data-stu-id="b3332-198">**Remove**</span></span>  
 <span data-ttu-id="b3332-199">Remova o InfoObject selecionado da lista **Atributos** .</span><span class="sxs-lookup"><span data-stu-id="b3332-199">Remove the selected InfoObject from the **Attributes** list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3332-200">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b3332-200">See Also</span></span>  
 <span data-ttu-id="b3332-201">[Criar InfoCube para os Dados da Transação](create-infocube-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="b3332-201">[Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md) </span></span>  
 <span data-ttu-id="b3332-202">[Criar InfoSource](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="b3332-202">[Create InfoSource](create-infosource.md) </span></span>  
 <span data-ttu-id="b3332-203">[Criar InfoSource para os dados da transação](create-infosource-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="b3332-203">[Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) </span></span>  
 <span data-ttu-id="b3332-204">[Criar InfoSource para dados mestre](create-infosource-for-master-data.md) </span><span class="sxs-lookup"><span data-stu-id="b3332-204">[Create InfoSource for Master Data](create-infosource-for-master-data.md) </span></span>  
 [<span data-ttu-id="b3332-205">Ajuda F1 do Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="b3332-205">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
