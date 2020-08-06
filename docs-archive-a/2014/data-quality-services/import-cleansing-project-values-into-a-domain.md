---
title: Importar valores de projeto de limpeza para um domínio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.importprojectvalues.f1
ms.assetid: f23e38e2-39e0-42d7-abd5-34d8fcca5d2a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 38616da5a0a8fb9c8f149d9f55a08b63dee5ff6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680637"
---
# <a name="import-cleansing-project-values-into-a-domain"></a><span data-ttu-id="244a7-102">Importar valores de projeto de limpeza para um domínio</span><span class="sxs-lookup"><span data-stu-id="244a7-102">Import Cleansing Project Values into a Domain</span></span>
  <span data-ttu-id="244a7-103">No [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS), você pode importar conhecimento de qualidade de dados coletado durante o processo de limpeza em um projeto de limpeza de qualidade de dados ou um pacote do Integration Services que contém o componente de limpeza DQS em um domínio.</span><span class="sxs-lookup"><span data-stu-id="244a7-103">In [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS), you can import data quality knowledge gathered during the cleansing process in a data quality cleansing project or an Integration Services package containing the DQS Cleansing component into a domain.</span></span> <span data-ttu-id="244a7-104">Isto assegura que o conhecimento confiável não seja perdido, e que a base de dados de conhecimento seja aprimorada continuamente.</span><span class="sxs-lookup"><span data-stu-id="244a7-104">This ensures that trusted knowledge is not lost, and that the knowledge base is continually improved.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="244a7-105">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="244a7-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="244a7-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="244a7-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="244a7-107">Para importar valores de projeto de limpeza para dentro de um domínio, o domínio deverá ter sido usado no projeto de limpeza no Cliente Data Quality ou no pacote do Integration Services que contém o componente de limpeza DQS.</span><span class="sxs-lookup"><span data-stu-id="244a7-107">To import cleansing project values into a domain, the domain must have been used in the cleansing project in Data Quality Client or in the Integration Services package containing a DQS Cleansing component.</span></span>  
  
-   <span data-ttu-id="244a7-108">O projeto de limpeza no Cliente Data Quality ou o pacote do Integration Services contendo o componente de limpeza DQS deve ter sido concluído com sucesso.</span><span class="sxs-lookup"><span data-stu-id="244a7-108">The cleansing project in Data Quality Client or the Integration Services package containing the DQS Cleansing component must have successfully completed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="244a7-109">Segurança</span><span class="sxs-lookup"><span data-stu-id="244a7-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="244a7-110">Permissões</span><span class="sxs-lookup"><span data-stu-id="244a7-110">Permissions</span></span>  
 <span data-ttu-id="244a7-111">Você deve ter a função dqs_kb_editor ou dqs_administrator no banco de dados DQS_MAIN para importar o conhecimento de qualidade de dados reunido durante o processo de limpeza para um domínio.</span><span class="sxs-lookup"><span data-stu-id="244a7-111">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to import data quality knowledge gathered during the cleansing process into a domain.</span></span>  
  
##  <a name="import-cleansing-project-values"></a><a name="Import"></a> <span data-ttu-id="244a7-112">Importar valores de projeto de limpeza</span><span class="sxs-lookup"><span data-stu-id="244a7-112">Import Cleansing Project Values</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="244a7-113">[Execute o aplicativo Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="244a7-113">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="244a7-114">Na tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , abra uma base de dados de conhecimento na atividade Gerenciamento de Domínio.</span><span class="sxs-lookup"><span data-stu-id="244a7-114">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, open a knowledge base in the Domain Management activity.</span></span>  
  
3.  <span data-ttu-id="244a7-115">Se estiver adicionando valores a um domínio existente, selecione o domínio na lista de domínios.</span><span class="sxs-lookup"><span data-stu-id="244a7-115">If adding values to an existing domain, select the domain in the domain list.</span></span>  
  
4.  <span data-ttu-id="244a7-116">Clique na guia **Valores de Domínio** , clique no ícone **Importar Valores** na barra de ícones e clique em **Importar valores do projeto**.</span><span class="sxs-lookup"><span data-stu-id="244a7-116">Click the **Domain Values** tab, click the **Import Values** icon in the icon bar, and then click **Import project values**.</span></span> <span data-ttu-id="244a7-117">A caixa de diálogo **Importar Valores do Projeto** é exibida com uma lista de projetos de qualidade de dados e pacotes do Integration Services que foram limpos usando o domínio.</span><span class="sxs-lookup"><span data-stu-id="244a7-117">The **Import Project Values** dialog box appears with a list of data quality projects and Integration Services packages that were cleansed using the domain.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="244a7-118">Se nenhum projeto tiver sido criado com o uso do domínio ou qualquer um de seus domínios vinculados ou o projeto não tiver sido terminado, a opção **Importar valores do projeto** não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="244a7-118">If no project has been created using the domain or any of its linked domains, or the project was not finished, the **Import project values** option will not be available.</span></span>  
  
5.  <span data-ttu-id="244a7-119">Na caixa de diálogo **Importar Valores do Projeto** :</span><span class="sxs-lookup"><span data-stu-id="244a7-119">In the **Import Project Values** dialog box:</span></span>  
  
    -   <span data-ttu-id="244a7-120">Selecione **Todos** na lista suspensa **Importado** para exibir todos os projetos ou **Nenhum** para exibir apenas os projetos cujos valores ainda não foram importados.</span><span class="sxs-lookup"><span data-stu-id="244a7-120">Select **All** in the **Imported** drop-down list to display all projects, or **No** to display only projects whose values have not been imported yet.</span></span>  
  
    -   <span data-ttu-id="244a7-121">Selecione o projeto a partir do qual você importará valores.</span><span class="sxs-lookup"><span data-stu-id="244a7-121">Select the project that you want to import values from.</span></span>  
  
    -   <span data-ttu-id="244a7-122">Selecione **Adicionar valores da guia Novo** para importar valores na guia Novo além dos valores nas guias **Corrigir** e **Corrigido** .</span><span class="sxs-lookup"><span data-stu-id="244a7-122">Select **Add values from New tab** to import values in the new tab, in addition to values in the **Correct** and **Corrected** tabs.</span></span>  
  
    -   <span data-ttu-id="244a7-123">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="244a7-123">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="244a7-124">Você retorna à guia **Valores do Domínio** e uma mensagem é exibida após a importação bem-sucedida dos valores.</span><span class="sxs-lookup"><span data-stu-id="244a7-124">You return to the **Domain Values** tab, and a message is displayed on successful import of the values.</span></span> <span data-ttu-id="244a7-125">Valores que foram importados e, portanto, são novos para o domínio serão exibidos na tabela **Valores** .</span><span class="sxs-lookup"><span data-stu-id="244a7-125">Values that have been imported, and so are new to the domain, will be displayed in the **Values** table.</span></span>  
  
7.  <span data-ttu-id="244a7-126">Desmarque **Mostrar Somente Novo** para exibir todos os valores no domínio.</span><span class="sxs-lookup"><span data-stu-id="244a7-126">Deselect **Show Only New** to display all values that are in the domain.</span></span>  
  
8.  <span data-ttu-id="244a7-127">Selecione **Corrigir**, **Erro**ou **Inválido** para exibir apenas os valores do tipo selecionado.</span><span class="sxs-lookup"><span data-stu-id="244a7-127">Select **Correct**, **Error**, or **Invalid** to display only those values of the selected type.</span></span>  
  
9. <span data-ttu-id="244a7-128">Para procurar uma cadeia de caracteres específica, insira essa cadeia de caracteres na caixa **Localizar** .</span><span class="sxs-lookup"><span data-stu-id="244a7-128">To search for a specific string, enter the string in the **Find** text box.</span></span> <span data-ttu-id="244a7-129">Clique na seta para cima ou para baixo para percorrer os valores que atendem os critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="244a7-129">Click the up or down arrow to step through the values that meet the search criteria.</span></span> <span data-ttu-id="244a7-130">Eles serão realçados em amarelo.</span><span class="sxs-lookup"><span data-stu-id="244a7-130">They will be highlighted in yellow.</span></span>  
  
10. <span data-ttu-id="244a7-131">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="244a7-131">Click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="244a7-132"> Para obter mais informações sobre como trabalhar com valores na página **Valores de Domínio** , consulte [Change Domain Values](../../2014/data-quality-services/change-domain-values.md).</span><span class="sxs-lookup"><span data-stu-id="244a7-132">For more information on working with values in the **Domain Values** tab, see [Change Domain Values](../../2014/data-quality-services/change-domain-values.md).</span></span>  
  
##  <a name="follow-up-after-importing-project-values-into-a-domain"></a><a name="FollowUp"></a> <span data-ttu-id="244a7-133">Acompanhamento: após a importação dos valores do projeto para um domínio</span><span class="sxs-lookup"><span data-stu-id="244a7-133">Follow Up: After Importing Project Values into a Domain</span></span>  
 <span data-ttu-id="244a7-134">Depois que você importar o conhecimento de qualidade de dados reunido durante o processo de limpeza para um domínio, você pode executar outras tarefas de gerenciamento de domínio no domínio e seus valores.</span><span class="sxs-lookup"><span data-stu-id="244a7-134">After you import data quality knowledge gathered during the cleansing process into a domain, you can perform other domain management tasks on the domain and the values.</span></span> <span data-ttu-id="244a7-135">Para obter mais informações, consulte [Gerenciando um domínio](../../2014/data-quality-services/managing-a-domain.md).</span><span class="sxs-lookup"><span data-stu-id="244a7-135">For more information, see [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md).</span></span>  
  
##  <a name="values-that-will-be-imported"></a><a name="Values"></a> <span data-ttu-id="244a7-136">Valores que serão importados</span><span class="sxs-lookup"><span data-stu-id="244a7-136">Values that Will Be Imported</span></span>  
 <span data-ttu-id="244a7-137">Os seguintes valores serão importados de um projeto para um domínio:</span><span class="sxs-lookup"><span data-stu-id="244a7-137">The following values will be imported from a project into a domain:</span></span>  
  
-   <span data-ttu-id="244a7-138">Somente valores da cadeia de caracteres são importados para o domínio.</span><span class="sxs-lookup"><span data-stu-id="244a7-138">Only string values are imported to the domain.</span></span>  
  
-   <span data-ttu-id="244a7-139">Apenas valores das guias **Correto**, **Corrigido**e **Novo** na página **Gerenciar e Exibir resultados** da atividade **Limpeza** serão importados.</span><span class="sxs-lookup"><span data-stu-id="244a7-139">Only values from the **Correct**, **Corrected**, and **New** tabs on the **Manage and View results** page of the **Cleansing** activity will be imported.</span></span> <span data-ttu-id="244a7-140">Os valores da guia **Novo** serão importados apenas se a caixa de seleção **Adicionar valores da guia Novo** estiver marcada na caixa de diálogo **Importar Valores do Projeto** .</span><span class="sxs-lookup"><span data-stu-id="244a7-140">Values from the **New** tab will be imported only if the **Add values from New tab** check box in the **Import Project Values** dialog box has been selected.</span></span>  
  
-   <span data-ttu-id="244a7-141">Os valores serão importados como corretos ou como um erro com sua correção.</span><span class="sxs-lookup"><span data-stu-id="244a7-141">Values will be imported as correct or as an error with its correction.</span></span> <span data-ttu-id="244a7-142">Somente um valor de erro com um valor de correção será importado.</span><span class="sxs-lookup"><span data-stu-id="244a7-142">Only an error value with a correction value will be imported.</span></span>  
  
-   <span data-ttu-id="244a7-143">O valor de correção será um novo valor que não existe na base de dados de conhecimento ou um valor correto existente.</span><span class="sxs-lookup"><span data-stu-id="244a7-143">The correction value will be either a new value that does not exist in the knowledge base or an existing correct value.</span></span>  
  
-   <span data-ttu-id="244a7-144">Somente as correções executadas no nível do valor, não no nível do registro serão importadas para a base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="244a7-144">Only corrections performed on the value level, not the record level, will be imported into the knowledge base.</span></span>  
  
-   <span data-ttu-id="244a7-145">Valores inválidos serão criados se o valor importado contrariar uma regra de domínio.</span><span class="sxs-lookup"><span data-stu-id="244a7-145">Invalid values will be created if the imported value contradicts a domain rule.</span></span>  
  
-   <span data-ttu-id="244a7-146">Se você importar valores de vários projetos de uma vez, os valores serão importados em sequência.</span><span class="sxs-lookup"><span data-stu-id="244a7-146">If you import values from several projects at once, the values are imported in a sequential order.</span></span>  
  
-   <span data-ttu-id="244a7-147">Uma correção feita em virtude de uma relação baseada em termo em um domínio é importada como um valor correto (não como um erro).</span><span class="sxs-lookup"><span data-stu-id="244a7-147">A correction made as a result of a term-based relation in a domain is imported as a correct value (not as an error).</span></span>  
  
##  <a name="values-that-will-not-be-imported"></a><a name="ValuesNot"></a> <span data-ttu-id="244a7-148">Valores que não serão importados</span><span class="sxs-lookup"><span data-stu-id="244a7-148">Values that Will Not Be Imported</span></span>  
 <span data-ttu-id="244a7-149">Os seguintes valores não serão importados de um projeto para um domínio:</span><span class="sxs-lookup"><span data-stu-id="244a7-149">The following values will not be imported from a project into a domain:</span></span>  
  
-   <span data-ttu-id="244a7-150">Valores das guias **Sugerido** e **Inválido** na página **Gerenciar e exibir resultados** da atividade **Limpeza** não serão importados.</span><span class="sxs-lookup"><span data-stu-id="244a7-150">Values from the **Suggested** and **Invalid** tabs on the **Manage and View results** page of the **Cleansing** activity will not be imported.</span></span>  
  
-   <span data-ttu-id="244a7-151">Se um valor encontrado no projeto de limpeza contrariar um valor existente no domínio, o valor encontrado no projeto será ignorado.</span><span class="sxs-lookup"><span data-stu-id="244a7-151">If a value found in the cleansing project contradicts an existing value in the domain, the value found in the project is skipped.</span></span> <span data-ttu-id="244a7-152">Isso incluirá conflitos entre os valores da base de dados de conhecimento e de limpeza.</span><span class="sxs-lookup"><span data-stu-id="244a7-152">This will include conflicts between cleansing and knowledge base values.</span></span>  
  
-   <span data-ttu-id="244a7-153">As correções executadas no nível do registro não serão importadas para a base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="244a7-153">Corrections performed on the record level will not be imported into the knowledge base.</span></span>  
  
-   <span data-ttu-id="244a7-154">Nenhum valor será importado para um domínio se o valor que ele substituiria fosse corrigido ou aprovado como correto por um serviço de dados de referência.</span><span class="sxs-lookup"><span data-stu-id="244a7-154">No value will be imported to a domain if the value that it would replace was corrected or approved as correct by a reference data service.</span></span>  
  
-   <span data-ttu-id="244a7-155">Se um valor de correção aparecer na base de dados de conhecimento como um valor inválido ou com erro, nem o valor com erro, nem o valor de correção serão importados.</span><span class="sxs-lookup"><span data-stu-id="244a7-155">If a correction value appears in the knowledge base as an invalid or error value, neither the error nor the correction value will be imported.</span></span>  
  
-   <span data-ttu-id="244a7-156">Se o domínio fizer parte de um domínio composto e a limpeza fosse executada no domínio composto, nenhum valor será importado.</span><span class="sxs-lookup"><span data-stu-id="244a7-156">If the domain is part of a composite domain, and the cleansing was performed on the composite domain, no values will be imported.</span></span>  
  
-   <span data-ttu-id="244a7-157">Você pode importar valores de um projeto somente quando a base de dados de conhecimento tem um estado de em funcionamento e está bloqueada pelo usuário realizando a importação.</span><span class="sxs-lookup"><span data-stu-id="244a7-157">You can import values from a project only when the knowledge base has a state of in-work and the knowledge base is locked by the user who is importing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="244a7-158">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="244a7-158">See Also</span></span>  
 <span data-ttu-id="244a7-159">[Limpeza de dados](../../2014/data-quality-services/data-cleansing.md) </span><span class="sxs-lookup"><span data-stu-id="244a7-159">[Data Cleansing](../../2014/data-quality-services/data-cleansing.md) </span></span>  
 [<span data-ttu-id="244a7-160">Transformação Limpeza DQS</span><span class="sxs-lookup"><span data-stu-id="244a7-160">DQS Cleansing Transformation</span></span>](../integration-services/data-flow/transformations/dqs-cleansing-transformation.md)  
  
  
