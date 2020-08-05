---
title: 'Etapa 3: Adicionando redirecionamento de fluxo de erro | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5683a45d-9e73-4cd5-83ca-fae8b26b488c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ceaea310cba05a940f310c01b52d5f912a53bea8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573180"
---
# <a name="step-3-adding-error-flow-redirection"></a><span data-ttu-id="52ded-102">Etapa 3: Adicionar redirecionamento de fluxo de erro</span><span class="sxs-lookup"><span data-stu-id="52ded-102">Step 3: Adding Error Flow Redirection</span></span>
  <span data-ttu-id="52ded-103">Conforme mostrado na tarefa anterior, a transformação Pesquisa de Códigos de Moeda não pode gerar uma correspondência quando a transformação tenta processar o arquivo simples de amostra corrompido que produziu um erro.</span><span class="sxs-lookup"><span data-stu-id="52ded-103">As demonstrated in the previous task, the Lookup Currency Key transformation cannot generate a match when the transformation tries to process the corrupted sample flat file, which produced an error.</span></span> <span data-ttu-id="52ded-104">Como a transformação usa as configurações padrão da saída de erro, qualquer erro faz a transformação falhar.</span><span class="sxs-lookup"><span data-stu-id="52ded-104">Because the transformation uses the default settings for error output, any error causes the transformation to fail.</span></span> <span data-ttu-id="52ded-105">Quando a transformação falha, o resto do pacote também falha.</span><span class="sxs-lookup"><span data-stu-id="52ded-105">When the transformation fails, the rest of the package also fails.</span></span>  
  
 <span data-ttu-id="52ded-106">Em vez de permitir a falha da transformação, você pode configurar o componente para redirecionar a linha com falha para outro caminho de processamento usando a saída de erro.</span><span class="sxs-lookup"><span data-stu-id="52ded-106">Instead of permitting the transformation to fail, you can configure the component to redirect the failed row to another processing path by using the error output.</span></span> <span data-ttu-id="52ded-107">O uso de um caminho de tratamento separado de erro permite que você faça várias coisas.</span><span class="sxs-lookup"><span data-stu-id="52ded-107">Use of a separate error processing path lets you do a number of things.</span></span> <span data-ttu-id="52ded-108">Por exemplo, você pode tentar limpar os dados e depois reprocessar a linha com falha.</span><span class="sxs-lookup"><span data-stu-id="52ded-108">For instance, you might try to clean the data and then reprocess the failed row.</span></span> <span data-ttu-id="52ded-109">Também é possível salvar a linha com falha junto com informações de erro adicionais para verificação e reprocessamento posteriores.</span><span class="sxs-lookup"><span data-stu-id="52ded-109">Or, you might save the failed row along with additional error information for later verification and reprocessing.</span></span>  
  
 <span data-ttu-id="52ded-110">Nesta tarefa, você configurará a transformação Pesquisa de Códigos de Moeda para redirecionar linhas com falha para a saída de erro.</span><span class="sxs-lookup"><span data-stu-id="52ded-110">In this task, you will configure the Lookup Currency Key transformation to redirect any rows that fail to the error output.</span></span> <span data-ttu-id="52ded-111">Na ramificação de erro do fluxo de dados, essas filas serão gravadas em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="52ded-111">In the error branch of the data flow, these rows will be written to a file.</span></span>  
  
 <span data-ttu-id="52ded-112">Por padrão as duas colunas extras em uma saída de erro do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , **ErrorCode** e **ErrorColumn**, só contêm códigos numéricos que representam um número de erro e a ID da coluna na qual o erro aconteceu.</span><span class="sxs-lookup"><span data-stu-id="52ded-112">By default the two extra columns in an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] error output, **ErrorCode** and **ErrorColumn**, contain only numeric codes that represent an error number, and the ID of the column in which the error occurred.</span></span> <span data-ttu-id="52ded-113">Esses valores numéricos podem ter uso limitado sem a descrição de erro correspondente.</span><span class="sxs-lookup"><span data-stu-id="52ded-113">These numeric values may be of limited use without the corresponding error description.</span></span>  
  
 <span data-ttu-id="52ded-114">Para aumentar a utilidade da saída de erro, antes de o pacote gravar as linhas com falha no arquivo, você usará um componente Script para acessar a API do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e obter uma descrição do erro.</span><span class="sxs-lookup"><span data-stu-id="52ded-114">To enhance the usefulness of the error output, before the package writes the failed rows to the file, you will use a Script component to access the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] API and get a description of the error.</span></span>  
  
### <a name="to-configure-an-error-output"></a><span data-ttu-id="52ded-115">Para configurar uma saída de erro</span><span class="sxs-lookup"><span data-stu-id="52ded-115">To configure an error output</span></span>  
  
1.  <span data-ttu-id="52ded-116">Na **caixa de ferramentas do SSIS**, expanda **comum**e arraste o **componente Script** para a superfície de design da guia **fluxo de dados** . Coloque o **script** à direita da transformação **Pesquisar chave de moeda** .</span><span class="sxs-lookup"><span data-stu-id="52ded-116">In the **SSIS Toolbox**, expand **Common**, and then drag **Script Component** onto the design surface of the **Data Flow** tab. Place **Script** to the right of the **Lookup Currency Key** transformation.</span></span>  
  
2.  <span data-ttu-id="52ded-117">Na caixa de diálogo **Selecionar Tipo de Componente do Script** , clique em **Transformação**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="52ded-117">In the **Select Script Component Type** dialog box, click **Transformation**, and click **OK**.</span></span>  
  
3.  <span data-ttu-id="52ded-118">Clique na transformação **Pesquisa de Códigos de Moeda** e depois arraste a seta vermelha sobre a transformação **Scripts** adicionada recentemente para conectar os dois componentes.</span><span class="sxs-lookup"><span data-stu-id="52ded-118">Click the **Lookup Currency Key** transformation and then drag the red arrow onto the newly added **Script** transformation to connect the two components.</span></span>  
  
     <span data-ttu-id="52ded-119">A seta vermelha representa a saída de erro da transformação **Pesquisa de Códigos de Moeda** .</span><span class="sxs-lookup"><span data-stu-id="52ded-119">The red arrow represents the error output of the **Lookup Currency Key** transformation.</span></span> <span data-ttu-id="52ded-120">Usando a seta vermelha para conectar a transformação ao componente Script, você pode redirecionar qualquer erro de processamento ao componente Script, que então processará os erros e os enviará ao destino.</span><span class="sxs-lookup"><span data-stu-id="52ded-120">By using the red arrow to connect the transformation to the Script component, you can redirect any processing errors to the Script component, which then processes the errors and sends them to the destination.</span></span>  
  
4.  <span data-ttu-id="52ded-121">Na caixa de diálogo **Configurar Saída de Erro** , na coluna **Erro** , selecione **Redirecionar linha**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="52ded-121">In the **Configure Error Output** dialog box, in the **Error** column, select **Redirect row**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="52ded-122">Na superfície de design **Fluxo de Dados** , clique em **Componente Script** , no **ScriptComponent**recém-adicionado e altere o nome para **Obter Descrição do Erro**.</span><span class="sxs-lookup"><span data-stu-id="52ded-122">On the **Data Flow** design surface, click **Script Component** in the newly added **ScriptComponent**, and change the name to **Get Error Description**.</span></span>  
  
6.  <span data-ttu-id="52ded-123">Clique duas vezes na transformação **Obter Descrição do Erro** .</span><span class="sxs-lookup"><span data-stu-id="52ded-123">Double-click the **Get Error Description** transformation.</span></span>  
  
7.  <span data-ttu-id="52ded-124">Na caixa de diálogo **Editor de Transformação Scripts** , na página **Colunas de Entrada** , selecione a coluna **ErrorCode** .</span><span class="sxs-lookup"><span data-stu-id="52ded-124">In the **Script Transformation Editor** dialog box, on the **Input Columns** page, select the **ErrorCode** column.</span></span>  
  
8.  <span data-ttu-id="52ded-125">Na página **Entradas e Saídas** , expanda **Saída 0**, clique em **Colunas de Saída**e clique em **Adicionar Coluna**.</span><span class="sxs-lookup"><span data-stu-id="52ded-125">On the **Inputs and Outputs** page, expand **Output 0**, click **Output Columns**, and then click **Add Column**.</span></span>  
  
9. <span data-ttu-id="52ded-126">Na `Name` propriedade, digite **ErrorDescription** e defina a `DataType` propriedade como cadeia de **caracteres Unicode [DT_WSTR]**.</span><span class="sxs-lookup"><span data-stu-id="52ded-126">In the `Name` property, type **ErrorDescription** and set the `DataType` property to **Unicode string [DT_WSTR]**.</span></span>  
  
10. <span data-ttu-id="52ded-127">Na página **script** , verifique se a `LocaleID` propriedade está definida como **Inglês (Estados Unidos.**</span><span class="sxs-lookup"><span data-stu-id="52ded-127">On the **Script** page, verify that the `LocaleID` property is set to **English (United States.**</span></span>  
  
11. <span data-ttu-id="52ded-128">Clique em **Editar Script** para abrir o [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] VSTA (Tools for Applications).</span><span class="sxs-lookup"><span data-stu-id="52ded-128">Click **Edit Script** to open [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span> <span data-ttu-id="52ded-129">No método `Input0_ProcessInputRow`, digite ou cole o código a seguir.</span><span class="sxs-lookup"><span data-stu-id="52ded-129">In the `Input0_ProcessInputRow` method, type or paste the following code.</span></span>  
  
     <span data-ttu-id="52ded-130">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="52ded-130">[Visual Basic]</span></span>  
  
    ```  
    Row.ErrorDescription =   
      Me.ComponentMetaData.GetErrorDescription(Row.ErrorCode)  
    ```  
  
     <span data-ttu-id="52ded-131">[Visual C#]</span><span class="sxs-lookup"><span data-stu-id="52ded-131">[Visual C#]</span></span>  
  
    ```  
    Row.ErrorDescription = this.ComponentMetaData.GetErrorDescription(Row.ErrorCode);  
    ```  
  
     <span data-ttu-id="52ded-132">A sub-rotina concluída se parecerá com o código a seguir.</span><span class="sxs-lookup"><span data-stu-id="52ded-132">The completed subroutine will look like the following code.</span></span>  
  
     <span data-ttu-id="52ded-133">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="52ded-133">[Visual Basic]</span></span>  
  
    ```  
    Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
      Row.ErrorDescription =   
        Me.ComponentMetaData.GetErrorDescription(Row.ErrorCode)  
  
    End Sub  
    ```  
  
     <span data-ttu-id="52ded-134">[Visual C#]</span><span class="sxs-lookup"><span data-stu-id="52ded-134">[Visual C#]</span></span>  
  
    ```  
    public override void Input0_ProcessInputRow(Input0Buffer Row)  
        {  
  
            Row.ErrorDescription = this.ComponentMetaData.GetErrorDescription(Row.ErrorCode);  
  
        }  
    ```  
  
12. <span data-ttu-id="52ded-135">No menu **Compilar** , clique em **Compilar solução** para criar o script, salvar suas alterações e fechar o VSTA.</span><span class="sxs-lookup"><span data-stu-id="52ded-135">On the **Build** menu, click **Build Solution** to build the script and save your changes, and then close VSTA.</span></span>  
  
13. <span data-ttu-id="52ded-136">Clique em **OK** para fechar a caixa de diálogo **Editor de Transformação Scripts** .</span><span class="sxs-lookup"><span data-stu-id="52ded-136">Click **OK** to close the **Script Transformation Editor** dialog box.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="52ded-137">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="52ded-137">Next Steps</span></span>  
 <span data-ttu-id="52ded-138">[Etapa 4: adicionando um destino de arquivo simples] (lesson-4-4-adding-a-flat-file-destination.md</span><span class="sxs-lookup"><span data-stu-id="52ded-138">[Step 4: Adding a Flat File Destination](lesson-4-4-adding-a-flat-file-destination.md</span></span>  
  
  
