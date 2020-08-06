---
title: 'Tarefa 13: adicionando OLE DB destino para gravar dados na tabela de preparo do MDS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: e6c67fa9-bb52-44a9-82f6-d86551cf12b2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 77799782518a3be2441b4c461467e3132781298d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680211"
---
# <a name="task-13-adding-ole-db-destination-to-write-data-to-mds-staging-table"></a><span data-ttu-id="b84e8-102">Tarefa 13: Adicionando o destino OLE DB para gravar dados na tabela de preparo do MDS</span><span class="sxs-lookup"><span data-stu-id="b84e8-102">Task 13: Adding OLE DB Destination to Write Data to MDS Staging Table</span></span>
  <span data-ttu-id="b84e8-103">Agora que você adicionou valores **importType** e **BatchTag** a todos os registros, você está pronto para enviá-los para o MDS para preparo.</span><span class="sxs-lookup"><span data-stu-id="b84e8-103">Now that you have added **ImportType** and **BatchTag** values to all records, you are ready to send them over to MDS for staging.</span></span> <span data-ttu-id="b84e8-104">Nesta tarefa, você usa o destino OLE DB para gravar os dados em **STG. supplier_Leaf** tabela de preparo.</span><span class="sxs-lookup"><span data-stu-id="b84e8-104">In this task, you use the OLE DB Destination to write the data into **stg.supplier_Leaf** staging table.</span></span>  
  
1.  <span data-ttu-id="b84e8-105">Arraste **OLE DB destino** de **outros destinos** seção na **caixa de ferramentas do SSIS** para a guia fluxo de **dados** e solte-o em **adicionar colunas exigidas pelo MDS**.</span><span class="sxs-lookup"><span data-stu-id="b84e8-105">Drag **OLE DB Destination** from **Other Destinations** section in the **SSIS Toolbox** to the **Data Flow** tab and drop it under **Add Columns Required by MDS**.</span></span>  
  
2.  <span data-ttu-id="b84e8-106">Clique com o botão direito do mouse **OLE DB destino** na guia **fluxo de dados** e clique em **renomear**.</span><span class="sxs-lookup"><span data-stu-id="b84e8-106">Right-click **OLE DB Destination** in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="b84e8-107">Digite **gravar dados do fornecedor na tabela de preparo do MDS** e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="b84e8-107">Type **Write Supplier Data to MDS Staging Table** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="b84e8-108">Conecte as **colunas de adição exigidas pelo MDS** para **gravar dados de fornecedor na tabela de preparo do MDS** usando o conector azul.</span><span class="sxs-lookup"><span data-stu-id="b84e8-108">Connect the **Add Columns Required by MDS** to **Write Supplier Data to MDS Staging Table** using the blue connector.</span></span>  
  
4.  <span data-ttu-id="b84e8-109">Clique duas vezes em **gravar dados do fornecedor na tabela de preparo do MDS** na guia fluxo de **dados** .</span><span class="sxs-lookup"><span data-stu-id="b84e8-109">Double-click **Write Supplier Data to MDS Staging Table** in the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="b84e8-110">Na caixa de diálogo **Editor de destino OLE DB** , verifique se **(local). MDS** (ou **localhost. MDS**) está selecionado para o campo **OLE DB Gerenciador de conexões** .</span><span class="sxs-lookup"><span data-stu-id="b84e8-110">In the **OLE DB Destination Editor** Dialog box, make sure that **(local).MDS** (or **localhost.MDS**) is selected for the **OLE DB Connection Manager** field.</span></span>  
  
6.  <span data-ttu-id="b84e8-111">Selecione **STG. Supplier_Leaf** tabela na lista de **nome da tabela ou exibição**.</span><span class="sxs-lookup"><span data-stu-id="b84e8-111">Select **stg.Supplier_Leaf** table from the list of **Name of the table or the view**.</span></span>  
  
     <span data-ttu-id="b84e8-112">![Editor de Destino de OLEDB](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-01.jpg "Editor de Destino de OLEDB")</span><span class="sxs-lookup"><span data-stu-id="b84e8-112">![OLEDB Destination Editor](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-01.jpg "OLEDB Destination Editor")</span></span>  
  
7.  <span data-ttu-id="b84e8-113">Alterne para a página **mapeamentos** clicando em **mapeamento** no menu à esquerda.</span><span class="sxs-lookup"><span data-stu-id="b84e8-113">Switch to the **Mappings** page by clicking **Mapping** on the menu on left.</span></span>  
  
8.  <span data-ttu-id="b84e8-114">Mapeie as colunas de **entrada** e de **destino** , conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b84e8-114">Map **input** and **destination** columns as shown in the following table.</span></span>  
  
     <span data-ttu-id="b84e8-115">![Editor de Destino OLEDB - Mapeamentos](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-02.jpg "Editor de Destino OLEDB - Mapeamentos")</span><span class="sxs-lookup"><span data-stu-id="b84e8-115">![OLEDB Destination Editor - Mappings](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-02.jpg "OLEDB Destination Editor - Mappings")</span></span>  
  
9. <span data-ttu-id="b84e8-116">Confirme se você está usando colunas **_Output** para colunas de entrada, não as colunas **_Status** ou **_Source** .</span><span class="sxs-lookup"><span data-stu-id="b84e8-116">Confirm that you are using **_Output** columns for Input Columns, not the **_Status** or **_Source** columns.</span></span> <span data-ttu-id="b84e8-117">**_Output** colunas contêm os valores de saída da limpeza DQS.</span><span class="sxs-lookup"><span data-stu-id="b84e8-117">**_Output** columns contain the output values from DQS Cleansing.</span></span>  
  
10. <span data-ttu-id="b84e8-118">Clique em **OK** para fechar a caixa de diálogo **OLE DB editor de destino** .</span><span class="sxs-lookup"><span data-stu-id="b84e8-118">Click **OK** to close the **OLE DB Destination Editor** dialog box.</span></span>  
  
11. <span data-ttu-id="b84e8-119">O fluxo de dados deve ter a aparência da imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="b84e8-119">The data flow should like the following image.</span></span>  
  
     <span data-ttu-id="b84e8-120">![Fluxo de dados concluído](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-03.jpg "Fluxo de dados concluído")</span><span class="sxs-lookup"><span data-stu-id="b84e8-120">![Completed Data Flow](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-03.jpg "Completed Data Flow")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="b84e8-121">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="b84e8-121">Next Step</span></span>  
 [<span data-ttu-id="b84e8-122">Tarefa 14: Adicionando a tarefa Executar SQL ao fluxo de controle para executar o procedimento armazenado para MDS</span><span class="sxs-lookup"><span data-stu-id="b84e8-122">Task 14: Adding Execute SQL Task to Control Flow to Run the Stored Procedure for MDS</span></span>](../../2014/tutorials/task-14-add-execute-to-control-flow-run-mds-stored-procedure.md)  
  
  
