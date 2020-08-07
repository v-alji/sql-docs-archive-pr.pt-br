---
title: Escolher um destino (Assistente de Importação e Exportação do SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.chooseadestination.f1
ms.assetid: 1898be15-3e69-42d3-8ecb-3733c9f6c8e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e4bf9b717ef9de20d84d32c18eb3caa4c54cad87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575949"
---
# <a name="choose-a-destination-sql-server-import-and-export-wizard"></a><span data-ttu-id="8a8ca-102">Escolher um destino (Assistente de Importação e Exportação do SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8a8ca-102">Choose a Destination (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="8a8ca-103">Use a página **escolher um destino** para especificar o destino dos dados que você deseja copiar.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-103">Use the **Choose a Destination** page to specify the destination of the data that you want to copy.</span></span>  
  
 <span data-ttu-id="8a8ca-104">Para obter mais informações sobre este assistente, consulte [Assistente de Importação e Exportação do SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="8a8ca-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="8a8ca-105">Para saber mais sobre as opções de inicialização do assistente, bem como as permissões necessárias para executar o assistente com êxito, consulte [executar o assistente de importação e exportação do SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="8a8ca-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="8a8ca-106">O objetivo do Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é copiar dados de uma origem para um destino.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-106">The purpose of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="8a8ca-107">O assistente também pode criar um banco de dados de destino e tabelas de destino para você.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="8a8ca-108">No entanto, se for necessário copiar vários bancos de dados ou tabelas, ou outros tipos de objetos de banco de dados, será necessário usar o Assistente para Copiar Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="8a8ca-109">Para obter mais informações, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="8a8ca-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="8a8ca-110">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="8a8ca-110">Static Options</span></span>  
 <span data-ttu-id="8a8ca-111">**Destino**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-111">**Destination**</span></span>  
 <span data-ttu-id="8a8ca-112">Escolha o provedor de dados que corresponde ao formato de armazenamento do destino.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-112">Choose the data provider that matches the data storage format of the destination.</span></span> <span data-ttu-id="8a8ca-113">Pode haver mais de um provedor disponível para sua fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-113">There may be more than one provider available for your data source.</span></span> <span data-ttu-id="8a8ca-114">Por exemplo, com [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o, você pode usar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o Native Client, o .NET Framework Provedor de Dados para SQL Server ou o provedor de OLE DB da Microsoft para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-114">For example, with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you can use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, the .NET Framework Data Provider for SQL Server, or the Microsoft OLE DB Provider for SQL Server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a8ca-115">Para salvar dados em um destino ODBC, selecione o Provedor de dados do .NET Framework para ODBC.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-115">To save data to an ODBC destination, select the .NET Framework Data Provider for ODBC.</span></span>  
  
 <span data-ttu-id="8a8ca-116">A propriedade **fonte de dados** tem um número variável de opções, que mudam dependendo dos provedores instalados no computador.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-116">The **Data Source** property has a variable number of options, which change depending on the providers installed on the computer.</span></span> <span data-ttu-id="8a8ca-117">As tabelas a seguir listam as opções para alguns destinos usados com frequência.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-117">The following tables list the options for some commonly used destinations.</span></span> <span data-ttu-id="8a8ca-118">Para outros provedores, consulte a documentação específica do provedor.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-118">For other providers, see the provider-specific documentation.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="8a8ca-119">Opções dinâmicas</span><span class="sxs-lookup"><span data-stu-id="8a8ca-119">Dynamic Options</span></span>  
 <span data-ttu-id="8a8ca-120">As seções a seguir mostram as opções disponíveis para várias fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-120">The following sections show the options available for several data sources.</span></span> <span data-ttu-id="8a8ca-121">Nem todos os destinos disponíveis no menu suspenso Destino são listados aqui.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-121">Not all the destinations that are available in the Destination drop-down are listed here.</span></span>  
  
### <a name="destination--sql-server-native-client-or-microsoft-ole-db-provider-for-sql-server"></a><span data-ttu-id="8a8ca-122">Destino = SQL Server Native Client ou Microsoft OLE DB Provider for SQL Server</span><span class="sxs-lookup"><span data-stu-id="8a8ca-122">Destination = SQL Server Native Client or Microsoft OLE DB Provider for SQL Server</span></span>  
 <span data-ttu-id="8a8ca-123">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-123">**Server name**</span></span>  
 <span data-ttu-id="8a8ca-124">Digite o nome do servidor que receberá os dados ou escolha um servidor da lista.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-124">Type the name of the server to receive the data, or choose a server from the list.</span></span>  
  
 <span data-ttu-id="8a8ca-125">**Usar Autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-125">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="8a8ca-126">Especifique se o pacote deve usar a Autenticação do Microsoft Windows para fazer login no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-126">Specify whether the package should use Microsoft Windows Authentication to log in to the database.</span></span> <span data-ttu-id="8a8ca-127">A Autenticação do Windows é recomendada para obter melhor segurança.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-127">Windows Authentication is recommended for better security.</span></span>  
  
 <span data-ttu-id="8a8ca-128">**Usar Autenticação do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-128">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="8a8ca-129">Especifique se o pacote deve usar a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para fazer login no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-129">Specify whether the package should use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication to log in to the database.</span></span> <span data-ttu-id="8a8ca-130">Se você usar a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , será preciso fornecer um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-130">If you use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="8a8ca-131">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-131">**User name**</span></span>  
 <span data-ttu-id="8a8ca-132">Especifique um nome de usuário para estabelecer conexão com o banco de dados quando estiver usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a8ca-132">Specify a user name for the database connection when you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="8a8ca-133">**Senha**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-133">**Password**</span></span>  
 <span data-ttu-id="8a8ca-134">Forneça uma senha para estabelecer conexão de banco de dados quando estiver usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a8ca-134">Provide the password for the database connection when you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="8a8ca-135">**Backup de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-135">**Database**</span></span>  
 <span data-ttu-id="8a8ca-136">Selecione a partir da lista de bancos de dados na instância especificada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou crie um novo, clicando em **novo**.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-136">Select from the list of databases on the specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or create a new database by clicking **New**.</span></span>  
  
 <span data-ttu-id="8a8ca-137">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-137">**Refresh**</span></span>  
 <span data-ttu-id="8a8ca-138">Restaure a lista de bancos de dados disponíveis clicando em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-138">Restore the list of available databases by clicking **Refresh**.</span></span>  
  
 <span data-ttu-id="8a8ca-139">**Novo**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-139">**New**</span></span>  
 <span data-ttu-id="8a8ca-140">Crie um novo banco de dados de destino usando a caixa de diálogo **criar banco** de dados.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-140">Create a new destination database by using the **Create Database** dialog box.</span></span>  
  
### <a name="destination--flat-file-destination"></a><span data-ttu-id="8a8ca-141">Destino = Destino de Arquivos Simples</span><span class="sxs-lookup"><span data-stu-id="8a8ca-141">Destination = Flat File Destination</span></span>  
 <span data-ttu-id="8a8ca-142">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-142">**File name**</span></span>  
 <span data-ttu-id="8a8ca-143">Especifique o caminho e o nome de arquivo do arquivo no qual deseja armazenar os dados.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-143">Specify the path and file name for the file in which to store the data.</span></span> <span data-ttu-id="8a8ca-144">Se preferir, clique em **Procurar** para localizar um arquivo.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-144">Or, click **Browse** to locate a file.</span></span>  
  
 <span data-ttu-id="8a8ca-145">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-145">**Browse**</span></span>  
 <span data-ttu-id="8a8ca-146">Localize um arquivo usando a caixa de diálogo **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-146">Locate a file by using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="8a8ca-147">**Localidade**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-147">**Locale**</span></span>  
 <span data-ttu-id="8a8ca-148">Especifique a ID de localidade (LCID) que define as ordens de classificação de caracteres e a formatação de data e hora.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-148">Specify the locale ID (LCID) that defines character sort orders and date and time formatting.</span></span>  
  
 <span data-ttu-id="8a8ca-149">**Unicode**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-149">**Unicode**</span></span>  
 <span data-ttu-id="8a8ca-150">Indique se deve ser usado o Unicode.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-150">Indicate whether to use Unicode.</span></span> <span data-ttu-id="8a8ca-151">Se decidir usá-lo, não será possível especificar uma página de códigos.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-151">If you use Unicode, you do not have to specify a code page.</span></span>  
  
 <span data-ttu-id="8a8ca-152">**Página de código**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-152">**Code page**</span></span>  
 <span data-ttu-id="8a8ca-153">Especifique a página de códigos da linguagem que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-153">Specify the code page for the language you want to use.</span></span>  
  
 <span data-ttu-id="8a8ca-154">**Formato**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-154">**Format**</span></span>  
 <span data-ttu-id="8a8ca-155">Indique se será usada formatação delimitada, de largura fixa ou irregular à direita.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-155">Indicate whether to use delimited, fixed width, or ragged right formatting.</span></span>  
  
|<span data-ttu-id="8a8ca-156">Valor</span><span class="sxs-lookup"><span data-stu-id="8a8ca-156">Value</span></span>|<span data-ttu-id="8a8ca-157">Descrição</span><span class="sxs-lookup"><span data-stu-id="8a8ca-157">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8a8ca-158">Delimitado</span><span class="sxs-lookup"><span data-stu-id="8a8ca-158">Delimited</span></span>|<span data-ttu-id="8a8ca-159">As colunas são separadas por um delimitador, especificado na página **colunas** .</span><span class="sxs-lookup"><span data-stu-id="8a8ca-159">Columns are separated by a delimiter, specified on the **Columns** page.</span></span>|  
|<span data-ttu-id="8a8ca-160">Largura fixa</span><span class="sxs-lookup"><span data-stu-id="8a8ca-160">Fixed width</span></span>|<span data-ttu-id="8a8ca-161">As colunas têm uma largura fixa.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-161">Columns have a fixed width.</span></span>|  
|<span data-ttu-id="8a8ca-162">Irregular à direita</span><span class="sxs-lookup"><span data-stu-id="8a8ca-162">Ragged right</span></span>|<span data-ttu-id="8a8ca-163">Nos arquivos irregulares à direita, todas as colunas têm uma largura fixa, com exceção da última, que é delimitada pelo delimitador de linha.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-163">Ragged right files are files in which every column has a fixed width, except for the last column, which is delimited by the row delimiter.</span></span>|  
  
 <span data-ttu-id="8a8ca-164">**Qualificador de texto**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-164">**Text qualifier**</span></span>  
 <span data-ttu-id="8a8ca-165">Digite o qualificador de texto a ser usado.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-165">Type the text qualifier to use.</span></span> <span data-ttu-id="8a8ca-166">Por exemplo, você pode especificar que cada coluna de texto seja destacada com aspas.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-166">For example, you can specify that each text column be surrounded with quotation marks.</span></span>  
  
 <span data-ttu-id="8a8ca-167">**Nomes de coluna na primeira linha de dados**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-167">**Column names in first data row**</span></span>  
 <span data-ttu-id="8a8ca-168">Indique se você deseja exibir os nomes de coluna na primeira linha de dados.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-168">Indicate whether you want to display column names in the first data row.</span></span>  
  
### <a name="destination--microsoft-excel"></a><span data-ttu-id="8a8ca-169">Destino = Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="8a8ca-169">Destination = Microsoft Excel</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a8ca-170">Selecione **Microsoft Excel** somente se você quiser se conectar a uma fonte de dados que usa o Excel 2003 ou anterior.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-170">Select **Microsoft Excel** only if you want to connect to a data source that uses Excel 2003 or earlier.</span></span> <span data-ttu-id="8a8ca-171">Para se conectar a uma fonte de dados que usa o Excel 2007, selecione **Microsoft Office 12,0 acesso mecanismo de banco de dados provedor de OLE DB**, clique em **Propriedades**e, em seguida, na guia **tudo** da caixa de diálogo Propriedades do **link de dados** , para **Propriedades estendidas**, digite `Excel 12.0` .</span><span class="sxs-lookup"><span data-stu-id="8a8ca-171">To connect to a data source that uses Excel 2007, select **Microsoft Office 12.0 Access Database Engine OLE DB Provider**, click **Properties**, and then on the **All** tab of the **Data Link Properties** dialog box, for **Extended Properties**, enter `Excel 12.0`.</span></span>  
  
 <span data-ttu-id="8a8ca-172">**Caminho de arquivo do Excel**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-172">**Excel file path**</span></span>  
 <span data-ttu-id="8a8ca-173">Especifique o caminho e o nome do arquivo para a pasta de trabalho na qual armazenar os dados (por exemplo, C:\MyData.xls, \\\Sales\Database\Northwind.xls).</span><span class="sxs-lookup"><span data-stu-id="8a8ca-173">Specify the path and file name for the workbook in which to store the data (for example, C:\MyData.xls, \\\Sales\Database\Northwind.xls).</span></span> <span data-ttu-id="8a8ca-174">Ou clique em **procurar** para localizar uma pasta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-174">Or, click **Browse** to locate a workbook.</span></span>  
  
 <span data-ttu-id="8a8ca-175">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-175">**Browse**</span></span>  
 <span data-ttu-id="8a8ca-176">Localize uma pasta de trabalho do Excel usando a caixa de diálogo **abrir** .</span><span class="sxs-lookup"><span data-stu-id="8a8ca-176">Locate an Excel workbook by using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="8a8ca-177">**Versão do Excel**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-177">**Excel version**</span></span>  
 <span data-ttu-id="8a8ca-178">Selecione a versão do Excel que será usada pela pasta de trabalho de destino.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-178">Select the version of Excel that is used by the destination workbook.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a8ca-179">Ao exportar dados a um destino do [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)], o assistente utilizará o componente [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Excel Destination.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-179">When you export data to a [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)] destination, the wizard uses the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Excel Destination component.</span></span> <span data-ttu-id="8a8ca-180">Para obter informações sobre algumas considerações de uso e problemas conhecidos, consulte [destino do Excel](../data-flow/excel-destination.md).</span><span class="sxs-lookup"><span data-stu-id="8a8ca-180">For information on some usage considerations and known issues, see [Excel Destination](../data-flow/excel-destination.md).</span></span>  
  
### <a name="destination--microsoft-access"></a><span data-ttu-id="8a8ca-181">Destino = Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="8a8ca-181">Destination = Microsoft Access</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a8ca-182">Selecione **Microsoft Access** somente se você quiser se conectar a um banco de dados que usa o Access 2003 ou anterior.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-182">Select **Microsoft Access** only if you want to connect to a database that uses Access 2003 or earlier.</span></span> <span data-ttu-id="8a8ca-183">Para se conectar a um banco de dados que usa o Access 2007, selecione **Microsoft Office mecanismo de banco de dados o provedor de OLE DB de acesso 12,0**.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-183">To connect to a database that uses Access 2007, select **Microsoft Office 12.0 Access Database Engine OLE DB Provider**.</span></span>  
  
 <span data-ttu-id="8a8ca-184">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-184">**File name**</span></span>  
 <span data-ttu-id="8a8ca-185">Especifique o caminho e o nome de arquivo para o arquivo de banco de dados no qual deseja armazená-los (por exemplo, C:\MyData.mdb, \\ \Sales\Database\Northwind.mdb).</span><span class="sxs-lookup"><span data-stu-id="8a8ca-185">Specify the path and file name for the database file in which to store the data (for example, C:\MyData.mdb, \\\Sales\Database\Northwind.mdb).</span></span> <span data-ttu-id="8a8ca-186">Ou clique em **procurar** para localizar um arquivo de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-186">Or, click **Browse** to locate a database file.</span></span>  
  
 <span data-ttu-id="8a8ca-187">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-187">**Browse**</span></span>  
 <span data-ttu-id="8a8ca-188">Navegue até o arquivo de banco de dados usando a caixa de diálogo **abrir** .</span><span class="sxs-lookup"><span data-stu-id="8a8ca-188">Browse to the database file by using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="8a8ca-189">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-189">**User name**</span></span>  
 <span data-ttu-id="8a8ca-190">Especifique um nome de usuário válido para estabelecer conexão com o banco de dados quando houver um arquivo de informações do grupo de trabalho associado ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-190">Specify a valid user name for the database connection when a workgroup information file is associated with the database.</span></span>  
  
 <span data-ttu-id="8a8ca-191">**Senha**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-191">**Password**</span></span>  
 <span data-ttu-id="8a8ca-192">Forneça a senha do usuário para estabelecer conexão quando o arquivo de informações do grupo de trabalho estiver associado ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-192">Provide the user's password for the database connection when a workgroup information file is associated with the database.</span></span> <span data-ttu-id="8a8ca-193">No entanto, se o banco de dados estiver protegido com uma única senha para todos os usuários, você deverá fornecer esse valor na caixa de diálogo **Propriedades do vínculo de dados** , que é acessada no botão **avançado** .</span><span class="sxs-lookup"><span data-stu-id="8a8ca-193">However, if the database is protected with a single password for all users, you must provide this value in the **Data Link Properties** dialog box, which is accessed from the **Advanced** button.</span></span>  
  
 <span data-ttu-id="8a8ca-194">**Avançado**</span><span class="sxs-lookup"><span data-stu-id="8a8ca-194">**Advanced**</span></span>  
 <span data-ttu-id="8a8ca-195">Especifique as opções avançadas, como a senha do banco de dados ou um arquivo de informações do grupo de trabalho não padrão, usando a caixa de diálogo **Propriedades de Vínculo de Dados**.</span><span class="sxs-lookup"><span data-stu-id="8a8ca-195">Specify advanced options, such as the database password or a non-default workgroup information file, by using the **Data Link Properties** dialog box.</span></span> <span data-ttu-id="8a8ca-196">Para obter mais informações sobre as propriedades do provedor de OLE DB, pesquise na seção de acesso a dados da [biblioteca MSDN](https://go.microsoft.com/fwlink/?linkid=62553).</span><span class="sxs-lookup"><span data-stu-id="8a8ca-196">For more information about OLE DB provider properties, search in the Data Access section of the [MSDN Library](https://go.microsoft.com/fwlink/?linkid=62553).</span></span>  
  
  
