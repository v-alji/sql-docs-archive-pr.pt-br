---
title: Executar o assistente de importação e exportação do SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Import and Export Wizard
- starting SQL Server Import and Export Wizard
- Import and Export Wizard
- starting Import and Export Wizard
ms.assetid: 5fc4f6d1-1f6f-444e-9aeb-827f85e1c405
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 008c541b1f1a295057b0ee7cc384982627b9689a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575920"
---
# <a name="run-the-sql-server-import-and-export-wizard"></a><span data-ttu-id="293ac-102">Executar o Assistente de Importação e Exportação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="293ac-102">Run the SQL Server Import and Export Wizard</span></span>
  <span data-ttu-id="293ac-103">O Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornece o método mais simples para criar pacotes básicos e copiar dados entre fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="293ac-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard provides the simplest method of copying data between data sources and of constructing basic packages.</span></span> <span data-ttu-id="293ac-104">Para obter mais informações sobre o assistente, consulte [SQL Server assistente de importação e exportação](import-and-export-data-with-the-sql-server-import-and-export-wizard.md)do.</span><span class="sxs-lookup"><span data-stu-id="293ac-104">For more information about the wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="293ac-105">Para um vídeo que demonstra como usar o SQL Server assistente de importação e exportação do para criar um pacote que exporta dados de um banco de SQL Server para uma planilha do Microsoft Excel, consulte [exportando dados SQL Server para o Excel (SQL Server vídeo)](https://go.microsoft.com/fwlink/?LinkId=131024).</span><span class="sxs-lookup"><span data-stu-id="293ac-105">For a video that demonstrates how to use the SQL Server Import and Export Wizard to create a package that exports data from a SQL Server database to a Microsoft Excel spreadsheet, see [Exporting SQL Server Data to Excel (SQL Server Video)](https://go.microsoft.com/fwlink/?LinkId=131024).</span></span>  
  
### <a name="to-start-the-sql-server-import-and-export-wizard"></a><span data-ttu-id="293ac-106">Para iniciar o Assistente de Importação e Exportação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="293ac-106">To start the SQL Server Import and Export Wizard</span></span>  
  
-   <span data-ttu-id="293ac-107">No menu **Iniciar** , aponte para **todos os programas**, aponte para**Microsoft SQL Server** e clique em **importar e exportar dados**.</span><span class="sxs-lookup"><span data-stu-id="293ac-107">On the **Start** menu, point to **All Programs**, point to**Microsoft SQL Server** , and then click **Import and Export Data**.</span></span>  
  
     <span data-ttu-id="293ac-108">- ou -</span><span class="sxs-lookup"><span data-stu-id="293ac-108">-or-</span></span>  
  
     <span data-ttu-id="293ac-109">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , clique com o botão direito do mouse na pasta **pacotes SSIS** e clique em **SSISImport e exportar assistente**.</span><span class="sxs-lookup"><span data-stu-id="293ac-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], right-click the **SSIS Packages** folder, and then click **SSISImport and Export Wizard**.</span></span>  
  
     <span data-ttu-id="293ac-110">- ou -</span><span class="sxs-lookup"><span data-stu-id="293ac-110">-or-</span></span>  
  
     <span data-ttu-id="293ac-111">No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , no menu **projeto** , clique em **SSISImport e exportar assistente**.</span><span class="sxs-lookup"><span data-stu-id="293ac-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Project** menu, click **SSISImport and Export Wizard**.</span></span>  
  
     <span data-ttu-id="293ac-112">- ou -</span><span class="sxs-lookup"><span data-stu-id="293ac-112">-or-</span></span>  
  
     <span data-ttu-id="293ac-113">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)] tipo de servidor, expanda bancos de dados, clique com o botão direito do mouse em um banco de dados, aponte para **tarefas**e, em seguida, clique em **Import data** ou **Export data**.</span><span class="sxs-lookup"><span data-stu-id="293ac-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] server type, expand Databases, right-click a database, point to **Tasks**, and then click **Import Data** or **Export data**.</span></span>  
  
     <span data-ttu-id="293ac-114">- ou -</span><span class="sxs-lookup"><span data-stu-id="293ac-114">-or-</span></span>  
  
     <span data-ttu-id="293ac-115">Em uma janela de prompt de comando, execute o DTSWizard.exe, localizado em C:\Arquivos de Programas\Microsoft SQL Server\100\DTS\Binn.</span><span class="sxs-lookup"><span data-stu-id="293ac-115">In a command prompt window, run DTSWizard.exe, located in C:\Program Files\Microsoft SQL Server\100\DTS\Binn.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="293ac-116">Em um computador de 64 bits, o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] instala a versão de 64 bits do Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (DTSWizard.exe).</span><span class="sxs-lookup"><span data-stu-id="293ac-116">On a 64-bit computer, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installs the 64-bit version of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard (DTSWizard.exe).</span></span> <span data-ttu-id="293ac-117">No entanto, algumas fontes de dados, como Access ou Excel, só têm um provedor de 32 bits disponível.</span><span class="sxs-lookup"><span data-stu-id="293ac-117">However, some data sources, such as Access or Excel, only have a 32-bit provider available.</span></span> <span data-ttu-id="293ac-118">Para funcionar com essas fontes de dados, talvez seja necessário instalar e executar a versão de 32 bits do assistente.</span><span class="sxs-lookup"><span data-stu-id="293ac-118">To work with these data sources, you might have to install and run the 32-bit version of the wizard.</span></span> <span data-ttu-id="293ac-119">Para instalar a versão de 32 bits do assistente, selecione Ferramentas de Cliente ou [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="293ac-119">To install the 32-bit version of the wizard, select either Client Tools or [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] during setup.</span></span>  
  
### <a name="to-import-or-export-data-by-using-the-sql-server-import-and-export-wizard"></a><span data-ttu-id="293ac-120">Para importar ou exportar dados usando o Assistente de Importação e Exportação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="293ac-120">To import or export data by using the SQL Server Import and Export Wizard</span></span>  
  
1.  <span data-ttu-id="293ac-121">Inicie o Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="293ac-121">Start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard.</span></span>  
  
2.  <span data-ttu-id="293ac-122">Nas páginas de assistente correspondentes, selecione uma fonte de dados e um destino de dados.</span><span class="sxs-lookup"><span data-stu-id="293ac-122">On the corresponding wizard pages, select a data source and a data destination.</span></span>  
  
     <span data-ttu-id="293ac-123">As fontes de dados disponíveis incluem provedores de dados [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], provedores OLE DB, provedores [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], provedores [!INCLUDE[vstecado](../../includes/vstecado-md.md)], Microsoft Office Excel, Microsoft Office Access e a fonte de arquivos simples.</span><span class="sxs-lookup"><span data-stu-id="293ac-123">The available data sources include [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data providers, OLE DB providers, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client providers, [!INCLUDE[vstecado](../../includes/vstecado-md.md)] providers, Microsoft Office Excel, Microsoft Office Access, and the Flat File source.</span></span> <span data-ttu-id="293ac-124">Dependendo da fonte, você define opções como modo de autenticação, nome do servidor, nome do banco de dados e formato do arquivo.</span><span class="sxs-lookup"><span data-stu-id="293ac-124">Depending on the source, you set options such as the authentication mode, server name, database name, and file format.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="293ac-125">O provedor [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB para Oracle não suporta os tipos de dados Oracle BLOB, CLOB, NCLOB, BFILE e UROWID.</span><span class="sxs-lookup"><span data-stu-id="293ac-125">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for Oracle does not support the Oracle BLOB, CLOB, NCLOB, BFILE, and UROWID data types.</span></span> <span data-ttu-id="293ac-126">Portanto, a origem de OLE DB não pode extrair dados de tabelas que contêm colunas com esses tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="293ac-126">Therefore, the OLE DB source cannot extract data from tables that contain columns with these data types.</span></span>  
  
     <span data-ttu-id="293ac-127">Os destinos de dados disponíveis incluem provedores de dados [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], provedores OLE DB, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, Excel, Access e o destino de arquivos simples.</span><span class="sxs-lookup"><span data-stu-id="293ac-127">The available data destinations include [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data providers, OLE DB providers, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, Excel, Access, and the Flat File destination.</span></span>  
  
3.  <span data-ttu-id="293ac-128">Defina as opções do tipo de destino que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="293ac-128">Set the options for the type of destination that you selected.</span></span>  
  
     <span data-ttu-id="293ac-129">Se o destino for um banco de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], você poderá especificar os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="293ac-129">If the destination is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database you can specify the following:</span></span>  
  
    -   <span data-ttu-id="293ac-130">Indique se deseja criar um banco de dados novo e definir as propriedades do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="293ac-130">Indicate whether to create a new database and set the database properties.</span></span> <span data-ttu-id="293ac-131">As propriedades a seguir não podem ser configuradas e o assistente usa os valores padrão especificados:</span><span class="sxs-lookup"><span data-stu-id="293ac-131">The following properties cannot be configured and the wizard uses the specified default values:</span></span>  
  
        |<span data-ttu-id="293ac-132">Propriedade</span><span class="sxs-lookup"><span data-stu-id="293ac-132">Property</span></span>|<span data-ttu-id="293ac-133">Valor</span><span class="sxs-lookup"><span data-stu-id="293ac-133">Value</span></span>|  
        |--------------|-----------|  
        |<span data-ttu-id="293ac-134">Collation</span><span class="sxs-lookup"><span data-stu-id="293ac-134">Collation</span></span>|<span data-ttu-id="293ac-135">Latin1_General_CS_AS_KS_WS</span><span class="sxs-lookup"><span data-stu-id="293ac-135">Latin1_General_CS_AS_KS_WS</span></span>|  
        |<span data-ttu-id="293ac-136">modelo de recuperação</span><span class="sxs-lookup"><span data-stu-id="293ac-136">Recovery model</span></span>|<span data-ttu-id="293ac-137">Completo</span><span class="sxs-lookup"><span data-stu-id="293ac-137">Full</span></span>|  
        |<span data-ttu-id="293ac-138">Usar indexação de texto completo</span><span class="sxs-lookup"><span data-stu-id="293ac-138">Use full-text indexing</span></span>|<span data-ttu-id="293ac-139">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="293ac-139">True</span></span>|  
  
    -   <span data-ttu-id="293ac-140">Escolha se deseja copiar dados de tabelas ou exibições ou copiar resultados de consulta.</span><span class="sxs-lookup"><span data-stu-id="293ac-140">Select whether to copy data from tables or views, or to copy query results.</span></span>  
  
         <span data-ttu-id="293ac-141">Se desejar consultar os dados de origem e copiar os resultados, você poderá criar uma consulta Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="293ac-141">If you want to query the source data and copy the results, you can construct a Transact-SQL query.</span></span> <span data-ttu-id="293ac-142">Você pode digitar a consulta Transact-SQL manualmente ou usar uma consulta salva em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="293ac-142">You can enter the Transact-SQL query manually or use a query saved to a file.</span></span> <span data-ttu-id="293ac-143">O assistente inclui um recurso de navegação para localizar o arquivo e o assistente abre o arquivo automaticamente e cola seu conteúdo na página do assistente quando você seleciona o arquivo.</span><span class="sxs-lookup"><span data-stu-id="293ac-143">The wizard includes a browse feature for locating the file, and the wizard automatically opens the file and pastes its content into the wizard page when you select the file.</span></span>  
  
         <span data-ttu-id="293ac-144">Se a fonte for um provedor [!INCLUDE[vstecado](../../includes/vstecado-md.md)], você também poderá usar a opção para copiar resultados da consulta, fornecendo a cadeia DBCommand como a consulta.</span><span class="sxs-lookup"><span data-stu-id="293ac-144">If the source is an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] provider you can also use the option to copy query results, providing the DBCommand string as the query.</span></span>  
  
         <span data-ttu-id="293ac-145">Se os dados da fonte forem uma exibição, o Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] converterá a exibição automaticamente para uma tabela no destino.</span><span class="sxs-lookup"><span data-stu-id="293ac-145">If the source data is a view, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard automatically converts the view to a table in the destination.</span></span>  
  
    -   <span data-ttu-id="293ac-146">Indique se a tabela de destino será descartada e recriada e se as inserções de identidade serão habilitadas.</span><span class="sxs-lookup"><span data-stu-id="293ac-146">Indicate whether the destination table is dropped and then re-created, and whether to enable identity inserts.</span></span>  
  
    -   <span data-ttu-id="293ac-147">Indique se você deseja excluir ou adicionar linhas a uma tabela de destino existente.</span><span class="sxs-lookup"><span data-stu-id="293ac-147">Indicate whether to delete rows or append rows in an existing destination table.</span></span> <span data-ttu-id="293ac-148">Se a tabela não existir, o Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a criará automaticamente.</span><span class="sxs-lookup"><span data-stu-id="293ac-148">If the table does not exist, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard automatically creates it.</span></span>  
  
     <span data-ttu-id="293ac-149">Se o destino for um destino de arquivo simples, você poderá especificar os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="293ac-149">If the destination is a Flat File destination you can specify the following:</span></span>  
  
    -   <span data-ttu-id="293ac-150">Especifique o delimitador de linhas no arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="293ac-150">Specify the row delimiter in the destination file.</span></span>  
  
    -   <span data-ttu-id="293ac-151">Especifique o delimitador de colunas no arquivo de destino.</span><span class="sxs-lookup"><span data-stu-id="293ac-151">Specify the column delimiter in the destination file.</span></span>  
  
4.  <span data-ttu-id="293ac-152">(Opcional) Selecione uma tabela e altere os mapeamentos entre as colunas de origem e destino ou altere os metadados das colunas de destino:</span><span class="sxs-lookup"><span data-stu-id="293ac-152">(Optional) Select one table and change the mappings between source and destination columns, or change the metadata of destination columns:</span></span>  
  
    -   <span data-ttu-id="293ac-153">Mapeie as colunas de origem para colunas de destino diferentes.</span><span class="sxs-lookup"><span data-stu-id="293ac-153">Map source columns to different destination columns.</span></span>  
  
    -   <span data-ttu-id="293ac-154">Altere o tipo de dados na coluna de destino.</span><span class="sxs-lookup"><span data-stu-id="293ac-154">Change the data type in the destination column.</span></span>  
  
    -   <span data-ttu-id="293ac-155">Defina o comprimento das colunas com tipos de dados de caractere.</span><span class="sxs-lookup"><span data-stu-id="293ac-155">Set the length of columns with character data types.</span></span>  
  
    -   <span data-ttu-id="293ac-156">Defina a precisão e a escala das colunas com tipos de dados numéricos.</span><span class="sxs-lookup"><span data-stu-id="293ac-156">Set the precision and scale of columns with numeric data types.</span></span>  
  
    -   <span data-ttu-id="293ac-157">Especifique se a coluna pode conter valores nulos.</span><span class="sxs-lookup"><span data-stu-id="293ac-157">Specify whether the column can contain null values.</span></span>  
  
5.  <span data-ttu-id="293ac-158">(Opcional) Selecione várias tabelas e atualize os metadados e as opções que serão aplicados a essas tabelas:</span><span class="sxs-lookup"><span data-stu-id="293ac-158">(Optional) Select multiple tables, and update the metadata and options to apply to those tables:</span></span>  
  
    -   <span data-ttu-id="293ac-159">Selecione um esquema de destino existente ou forneça um novo esquema ao qual as tabelas serão atribuídas.</span><span class="sxs-lookup"><span data-stu-id="293ac-159">Select an existing destination schema or provide a new schema to which to assign tables.</span></span>  
  
    -   <span data-ttu-id="293ac-160">Especifique se deseja habilitar as inserções de identidade em tabelas de destino.</span><span class="sxs-lookup"><span data-stu-id="293ac-160">Specify whether to enable identity inserts in destination tables.</span></span>  
  
    -   <span data-ttu-id="293ac-161">Especifique se deseja descartar e recriar tabelas de destino.</span><span class="sxs-lookup"><span data-stu-id="293ac-161">Specify whether to drop and re-create destination tables.</span></span>  
  
    -   <span data-ttu-id="293ac-162">Especifique se deseja truncar as tabelas de destino existentes.</span><span class="sxs-lookup"><span data-stu-id="293ac-162">Specify whether to truncate existing destination tables.</span></span>  
  
6.  <span data-ttu-id="293ac-163">Salvar e executar um pacote.</span><span class="sxs-lookup"><span data-stu-id="293ac-163">Save and run a package.</span></span>  
  
     <span data-ttu-id="293ac-164">Se o assistente for iniciado no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou no prompt de comando, o pacote poderá ser executado imediatamente.</span><span class="sxs-lookup"><span data-stu-id="293ac-164">If the wizard is started from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or the command prompt, the package can run immediately.</span></span> <span data-ttu-id="293ac-165">Opcionalmente, você pode salvar o pacote no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] banco de dados **msdb** ou no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="293ac-165">You can optionally save the package to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **msdb** database or to the file system.</span></span> <span data-ttu-id="293ac-166">Para obter mais informações sobre o banco de dados **msdb** , consulte [Gerenciamento de pacotes &#40;&#41;do serviço SSIS ](../service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="293ac-166">For more information about the **msdb** database, see [Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md).</span></span>  
  
     <span data-ttu-id="293ac-167">Ao salvar o pacote, você poder definir o nível de proteção do pacote e, se esse nível de proteção usar uma senha, fornecer a senha.</span><span class="sxs-lookup"><span data-stu-id="293ac-167">When you save the package you can set the package protection level, and if the protection level uses a password, provide the password.</span></span> <span data-ttu-id="293ac-168">Para obter mais informações sobre os níveis de proteção do pacote, consulte [controle de acesso para dados confidenciais em pacotes](../security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="293ac-168">For more information about package protection levels, see [Access Control for Sensitive Data in Packages](../security/access-control-for-sensitive-data-in-packages.md).</span></span>  
  
     <span data-ttu-id="293ac-169">Se o assistente for iniciado a partir de um projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], não será possível executar o pacote a partir do assistente.</span><span class="sxs-lookup"><span data-stu-id="293ac-169">If the wizard is started from an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you cannot run the package from the wizard.</span></span> <span data-ttu-id="293ac-170">Em vez disso, o pacote será adicionado ao projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] a partir do qual você iniciou o assistente.</span><span class="sxs-lookup"><span data-stu-id="293ac-170">Instead, the package is added to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project from which you started the wizard.</span></span> <span data-ttu-id="293ac-171">Você poderá então executar o pacote no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="293ac-171">You can then run the package in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="293ac-172">No [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] , a opção para salvar o pacote criado pelo assistente não está disponível.</span><span class="sxs-lookup"><span data-stu-id="293ac-172">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], the option to save the package created by the wizard is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="293ac-173">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="293ac-173">See Also</span></span>  
 <span data-ttu-id="293ac-174">[Assistente de importação e exportação do SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="293ac-174">[SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md) </span></span>  
 [<span data-ttu-id="293ac-175">Criar pacotes nas Ferramentas de Dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="293ac-175">Create Packages in SQL Server Data Tools</span></span>](../create-packages-in-sql-server-data-tools.md)  
  
  
