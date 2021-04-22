# Omi Lua Wireshark Dissectors

[![Open-Markets-Initiative](https://circleci.com/github/Open-Markets-Initiative/wireshark-lua.svg?style=svg)](https://circleci.com/github/Open-Markets-Initiative/wireshark-lua)

Omi Lua Wireshark dissector scripts provide easily customized cross platform dissection solutions for viewing common binary exchange protocols.

For more information on lua dissectors: [How Lua fits into Wireshark](https://www.wireshark.org/docs/wsdg_html_chunked/wsluarm.html "Wireshark Lua Documentation")

## Usage

To dissect packets, place lua script(s) in the wireshark plugins directory.

The standard user path on a windows install (please create the plugins directory):

```
%APPDATA%\Wireshark\plugins\
```
On a linux install use:

```
//usr/share/wireshark/plugins
```
For configuration information: [Wireshark Plugin Configuration](https://www.wireshark.org/docs/wsug_html_chunked/ChPluginFolders.html "Wireshark Configuration Documentation")

Note: Some packets contain enough information to programmatically determine the correct protocol specification and/or version at runtime.  *Many do not.*  If you add multiple dissectors to your plugins folder, wireshark will dissect each "conversation" based on the first matching protocol.  In these cases, please manually select protocol dissector using Analyze | Decode As….

For decoding information: [Wireshark Protocol Decoding](https://www.wireshark.org/docs/wsug_html_chunked/ChCustProtocolDissectionSection.html "Wireshark Protocol Selection Documentation")
## Active Protocols

| Organization | Division | Data | Protocol | Version | Date | [Testing][Omi.Glossary.Testing] |
| --- | --- | --- | --- | --- | --- | --- |
| [Asx][Asx.Directory] | Securities | [Ntp][Asx.Securities.Ntp.Itch.v1.05.Dissector] | Itch | [1.05][Asx.Securities.Ntp.Itch.v1.05.Dissector] | 12/1/2017 | [Verified][Omi.Glossary.Testing.Verified] |
| [Cboe][Cboe.Directory] | Bzx Equities | [OrderEntry][Cboe.Bzx.Equities.OrderEntry.Boe.v2.3.Dissector] | Boe | [2.3][Cboe.Bzx.Equities.OrderEntry.Boe.v2.3.Dissector] | 3/11/2019 | [Incomplete][Omi.Glossary.Testing.Incomplete] |
| [Cboe][Cboe.Directory] | Bzx Options | [OrderEntry][Cboe.Bzx.Options.OrderEntry.Boe.v2.10.Dissector] | Boe | [2.10][Cboe.Bzx.Options.OrderEntry.Boe.v2.10.Dissector] | 12/3/2019 | [Incomplete][Omi.Glossary.Testing.Incomplete] |
| [Cboe][Cboe.Directory] | C1 Options | [OrderEntry][Cboe.C1.Options.OrderEntry.Boe.v2.10.Dissector] | Boe | [2.10][Cboe.C1.Options.OrderEntry.Boe.v2.10.Dissector] | 12/3/2019 | [Incomplete][Omi.Glossary.Testing.Incomplete] |
| [Cboe][Cboe.Directory] | C1 Options | [AuctionFeed][Cboe.C1.Options.AuctionFeed.Pitch.v1.1.1.Dissector] | Pitch | [1.1.1][Cboe.C1.Options.AuctionFeed.Pitch.v1.1.1.Dissector] | 12/6/2018 | [Verified][Omi.Glossary.Testing.Verified] |
| [Cboe][Cboe.Directory] | Edgx Equities | [OrderEntry][Cboe.Edgx.Equities.OrderEntry.Boe.v2.3.Dissector] | Boe | [2.3][Cboe.Edgx.Equities.OrderEntry.Boe.v2.3.Dissector] | 3/11/2019 | [Incomplete][Omi.Glossary.Testing.Incomplete] |
| [Cboe][Cboe.Directory] | Edgx Options | [OrderEntry][Cboe.Edgx.Options.OrderEntry.Boe.v2.10.Dissector] | Boe | [2.10][Cboe.Edgx.Options.OrderEntry.Boe.v2.10.Dissector] | 12/3/2019 | [Incomplete][Omi.Glossary.Testing.Incomplete] |
| [Cboe][Cboe.Directory] | Edgx Options | [AuctionFeed][Cboe.Edgx.Options.AuctionFeed.Pitch.v1.1.1.Dissector] | Pitch | [1.1.1][Cboe.Edgx.Options.AuctionFeed.Pitch.v1.1.1.Dissector] | 12/6/2018 | [Verified][Omi.Glossary.Testing.Verified] |
| [Cboe][Cboe.Directory] | Futures | [OrderEntry][Cboe.Futures.OrderEntry.Boe.v1.3.Dissector] | Boe | [1.3][Cboe.Futures.OrderEntry.Boe.v1.3.Dissector] | 4/21/2020 | [Incomplete][Omi.Glossary.Testing.Incomplete] |
| [Cboe][Cboe.Directory] | Futures | [DepthOfBook][Cboe.Futures.DepthOfBook.Pitch.v1.1.12.Dissector] | Pitch | [1.1.12][Cboe.Futures.DepthOfBook.Pitch.v1.1.12.Dissector] | 1/12/2021 | [Verified][Omi.Glossary.Testing.Verified] |
| [Cboe][Cboe.Directory] | Options | [ComplexDepthOfBook][Cboe.Options.ComplexDepthOfBook.Pitch.v2.1.18.Dissector] | Pitch | [2.1.18][Cboe.Options.ComplexDepthOfBook.Pitch.v2.1.18.Dissector] | 1/31/2020 | [Untested][Omi.Glossary.Testing.Untested] |
| [Cboe][Cboe.Directory] | Options | [DepthOfBook][Cboe.Options.DepthOfBook.Pitch.v2.39.4.Dissector] | Pitch | [2.39.4][Cboe.Options.DepthOfBook.Pitch.v2.39.4.Dissector] | 8/21/2018 | [Verified][Omi.Glossary.Testing.Verified] |
| [Cme][Cme.Directory] | Futures | [iLink3][Cme.Futures.iLink3.Sbe.v8.7.Dissector] | Sbe | [8.7][Cme.Futures.iLink3.Sbe.v8.7.Dissector] | 1/6/2021 | [Verified][Omi.Glossary.Testing.Verified] |
| [Cme][Cme.Directory] | Futures | [Mdp3][Cme.Futures.Mdp3.Sbe.v1.11.Dissector] | Sbe | [1.11][Cme.Futures.Mdp3.Sbe.v1.11.Dissector] | 3/3/2020 | [Untested][Omi.Glossary.Testing.Untested] |
| [Cme][Cme.Directory] | Futures | [Settlements][Cme.Futures.Settlements.Sbe.v7.0.Dissector] | Sbe | [7.0][Cme.Futures.Settlements.Sbe.v7.0.Dissector] | 12/3/2018 | [Untested][Omi.Glossary.Testing.Untested] |
| [Cme][Cme.Directory] | Futures | [Streamline][Cme.Futures.Streamline.Sbe.v5.9.Dissector] | Sbe | [5.9][Cme.Futures.Streamline.Sbe.v5.9.Dissector] | 4/4/2018 | [Untested][Omi.Glossary.Testing.Untested] |
| [Eurex][Eurex.Directory] | Cash | [Eti][Eurex.Cash.Eti.T7.v9.0.Dissector] | T7 | [9.0][Eurex.Cash.Eti.T7.v9.0.Dissector] | 8/10/2020 | [Untested][Omi.Glossary.Testing.Untested] |
| [Eurex][Eurex.Directory] | Derivatives | [Eobi][Eurex.Derivatives.Eobi.T7.v9.0.Dissector] | T7 | [9.0][Eurex.Derivatives.Eobi.T7.v9.0.Dissector] | 7/24/2020 | [Untested][Omi.Glossary.Testing.Untested] |
| [Eurex][Eurex.Directory] | Derivatives | [Eti][Eurex.Derivatives.Eti.T7.v9.0.Dissector] | T7 | [9.0][Eurex.Derivatives.Eti.T7.v9.0.Dissector] | 8/10/2020 | [Untested][Omi.Glossary.Testing.Untested] |
| [Euronext][Euronext.Directory] | Optiq | [MarketDataGateway][Euronext.Optiq.MarketDataGateway.Sbe.v4.3.0.Dissector] | Sbe | [4.3.0][Euronext.Optiq.MarketDataGateway.Sbe.v4.3.0.Dissector] | 9/25/2020 | [Beta][Omi.Glossary.Testing.Beta] |
| [Euronext][Euronext.Directory] | Optiq | [OrderEntryGateway][Euronext.Optiq.OrderEntryGateway.Sbe.v4.2.2.Dissector] | Sbe | [4.2.2][Euronext.Optiq.OrderEntryGateway.Sbe.v4.2.2.Dissector] | 9/25/2020 | [Beta][Omi.Glossary.Testing.Beta] |
| [Finra][Finra.Directory] | Orf | [Tdds][Finra.Orf.Tdds.Dfi.v2.0.Dissector] | Dfi | [2.0][Finra.Orf.Tdds.Dfi.v2.0.Dissector] | 9/24/2018 | [Verified][Omi.Glossary.Testing.Verified] |
| [Finra][Finra.Directory] | Otc | [Bbds][Finra.Otc.Bbds.Dfi.v2018.1A.Dissector] | Dfi | [2018.1A][Finra.Otc.Bbds.Dfi.v2018.1A.Dissector] | 5/14/2018 | [Untested][Omi.Glossary.Testing.Untested] |
| [Ice][Ice.Directory] | Futures | [Mdf][Ice.Futures.Mdf.iMpact.v1.1.34.Dissector] | iMpact | [1.1.34][Ice.Futures.Mdf.iMpact.v1.1.34.Dissector] | 9/4/2018 | [Verified][Omi.Glossary.Testing.Verified] |
| [Iex][Iex.Directory] | Equities | [Deep][Iex.Equities.Deep.IexTp.v1.0.Dissector] | IexTp | [1.0][Iex.Equities.Deep.IexTp.v1.0.Dissector] | 2/27/2018 | [Verified][Omi.Glossary.Testing.Verified] |
| [Iex][Iex.Directory] | Equities | [Tops][Iex.Equities.Tops.IexTp.v1.6.Dissector] | IexTp | [1.6][Iex.Equities.Tops.IexTp.v1.6.Dissector] | 2/27/2018 | [Verified][Omi.Glossary.Testing.Verified] |
| [Lse][Lse.Directory] | Millennium | [Level2][Lse.Millennium.Level2.Mitch.v11.9.Dissector] | Mitch | [11.9][Lse.Millennium.Level2.Mitch.v11.9.Dissector] | 8/28/2018 | [Beta][Omi.Glossary.Testing.Beta] |
| [Memx][Memx.Directory] | Equities | [Memo][Memx.Equities.Memo.Sbe.v1.2.Dissector] | Sbe | [1.2][Memx.Equities.Memo.Sbe.v1.2.Dissector] | 9/23/2020 | [Beta][Omi.Glossary.Testing.Beta] |
| [Memx][Memx.Directory] | Equities | [Memo][Memx.Equities.Memo.Sbe.v1.1.Dissector] | Sbe | [1.1][Memx.Equities.Memo.Sbe.v1.1.Dissector] | 7/27/2020 | [Beta][Omi.Glossary.Testing.Beta] |
| [Memx][Memx.Directory] | Equities | [MemoirDepthFeed][Memx.Equities.MemoirDepthFeed.Sbe.v1.1.Dissector] | Sbe | [1.1][Memx.Equities.MemoirDepthFeed.Sbe.v1.1.Dissector] | 7/27/2020 | [Beta][Omi.Glossary.Testing.Beta] |
| [Memx][Memx.Directory] | Equities | [MemoirLastSale][Memx.Equities.MemoirLastSale.Sbe.v1.1.Dissector] | Sbe | [1.1][Memx.Equities.MemoirLastSale.Sbe.v1.1.Dissector] | 7/27/2020 | [Beta][Omi.Glossary.Testing.Beta] |
| [Memx][Memx.Directory] | Equities | [MemoirTopOfBook][Memx.Equities.MemoirTopOfBook.Sbe.v1.1.Dissector] | Sbe | [1.1][Memx.Equities.MemoirTopOfBook.Sbe.v1.1.Dissector] | 7/27/2020 | [Beta][Omi.Glossary.Testing.Beta] |
| [Miax][Miax.Directory] | Options | [ComplexTopOfMarket][Miax.Options.ComplexTopOfMarket.Mach.v1.3.Dissector] | Mach | [1.3][Miax.Options.ComplexTopOfMarket.Mach.v1.3.Dissector] | 3/16/2018 | [Untested][Omi.Glossary.Testing.Untested] |
| [Miax][Miax.Directory] | Options | [TopOfMarket][Miax.Options.TopOfMarket.Mach.v2.3.Dissector] | Mach | [2.3][Miax.Options.TopOfMarket.Mach.v2.3.Dissector] | 6/10/2019 | [Untested][Omi.Glossary.Testing.Untested] |
| [Miax][Miax.Directory] | Options | [TopOfMarket][Miax.Options.TopOfMarket.Mach.v2.2.Dissector] | Mach | [2.2][Miax.Options.TopOfMarket.Mach.v2.2.Dissector] | 3/16/2018 | [Untested][Omi.Glossary.Testing.Untested] |
| [Miax][Miax.Directory] | Pearl Equities | [DepthOfMarket][Miax.Pearl.Equities.DepthOfMarket.Mach.v1.3.a.Dissector] | Mach | [1.3.a][Miax.Pearl.Equities.DepthOfMarket.Mach.v1.3.a.Dissector] | 11/5/2020 | [Untested][Omi.Glossary.Testing.Untested] |
| [Miax][Miax.Directory] | Pearl Equities | [TopOfMarket][Miax.Pearl.Equities.TopOfMarket.Mach.v1.1.a.Dissector] | Mach | [1.1.a][Miax.Pearl.Equities.TopOfMarket.Mach.v1.1.a.Dissector] | 11/5/2020 | [Untested][Omi.Glossary.Testing.Untested] |
| [Miax][Miax.Directory] | Pearl Options | [TopOfMarket][Miax.Pearl.Options.TopOfMarket.Mach.v1.0.Dissector] | Mach | [1.0][Miax.Pearl.Options.TopOfMarket.Mach.v1.0.Dissector] | 2/27/2017 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nasdaq][Nasdaq.Directory] |  Equities | [Orders][Nasdaq.Equities.Orders.Ouch.v4.2.Dissector] | Ouch | [4.2][Nasdaq.Equities.Orders.Ouch.v4.2.Dissector] | 7/8/2019 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nasdaq][Nasdaq.Directory] | Bx Equities | [TotalView][Nasdaq.Bx.Equities.TotalView.Itch.v5.0.Dissector] | Itch | [5.0][Nasdaq.Bx.Equities.TotalView.Itch.v5.0.Dissector] | 5/23/2018 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nasdaq][Nasdaq.Directory] | Bx Equities | [Orders][Nasdaq.Bx.Equities.Orders.Ouch.v4.2.Dissector] | Ouch | [4.2][Nasdaq.Bx.Equities.Orders.Ouch.v4.2.Dissector] | 7/8/2019 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nasdaq][Nasdaq.Directory] | Bx Options | [DepthOfMarket][Nasdaq.Bx.Options.DepthOfMarket.Itch.v1.3.Dissector] | Itch | [1.3][Nasdaq.Bx.Options.DepthOfMarket.Itch.v1.3.Dissector] | 11/2/2017 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nasdaq][Nasdaq.Directory] | Bx Options | [TopOfMarket][Nasdaq.Bx.Options.TopOfMarket.Itch.v1.2.Dissector] | Itch | [1.2][Nasdaq.Bx.Options.TopOfMarket.Itch.v1.2.Dissector] | 11/2/2017 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nasdaq][Nasdaq.Directory] | Equities | [Aggregated][Nasdaq.Equities.Aggregated.Itch.v2.0.Dissector] | Itch | [2.0][Nasdaq.Equities.Aggregated.Itch.v2.0.Dissector] | 9/12/2017 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nasdaq][Nasdaq.Directory] | Equities | [Level2][Nasdaq.Equities.Level2.Itch.v2.0.Dissector] | Itch | [2.0][Nasdaq.Equities.Level2.Itch.v2.0.Dissector] | 5/3/2018 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nasdaq][Nasdaq.Directory] | Equities | [Noi][Nasdaq.Equities.Noi.Itch.v3.0.Dissector] | Itch | [3.0][Nasdaq.Equities.Noi.Itch.v3.0.Dissector] | 9/12/2017 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nasdaq][Nasdaq.Directory] | Equities | [TotalView][Nasdaq.Equities.TotalView.Itch.v5.0.Dissector] | Itch | [5.0][Nasdaq.Equities.TotalView.Itch.v5.0.Dissector] | 9/12/2017 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nasdaq][Nasdaq.Directory] | Ise | [OrderComboFeed][Nasdaq.Ise.OrderComboFeed.Itch.v1.1.Dissector] | Itch | [1.1][Nasdaq.Ise.OrderComboFeed.Itch.v1.1.Dissector] | 6/13/2017 | [Verified][Omi.Glossary.Testing.Verified] |
| [Nasdaq][Nasdaq.Directory] | Ise | [OrderFeed][Nasdaq.Ise.OrderFeed.Itch.v1.1.Dissector] | Itch | [1.1][Nasdaq.Ise.OrderFeed.Itch.v1.1.Dissector] | 8/23/2017 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nasdaq][Nasdaq.Directory] | Ise | [TopComboQuoteFeed][Nasdaq.Ise.TopComboQuoteFeed.Itch.v1.0.Dissector] | Itch | [1.0][Nasdaq.Ise.TopComboQuoteFeed.Itch.v1.0.Dissector] | 8/23/2017 | [Verified][Omi.Glossary.Testing.Verified] |
| [Nasdaq][Nasdaq.Directory] | Nom | [Bono][Nasdaq.Nom.Bono.Itch.v3.2.Dissector] | Itch | [3.2][Nasdaq.Nom.Bono.Itch.v3.2.Dissector] | 11/2/2017 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nasdaq][Nasdaq.Directory] | Nom | [Itto][Nasdaq.Nom.Itto.Itch.v4.0.Dissector] | Itch | [4.0][Nasdaq.Nom.Itto.Itch.v4.0.Dissector] | 2/8/2018 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nasdaq][Nasdaq.Directory] | Phlx | [MarketDepth][Nasdaq.Phlx.MarketDepth.Itch.v1.6.Dissector] | Itch | [1.6][Nasdaq.Phlx.MarketDepth.Itch.v1.6.Dissector] | 3/8/2018 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nasdaq][Nasdaq.Directory] | Phlx | [Orders][Nasdaq.Phlx.Orders.Itch.v1.9.Dissector] | Itch | [1.9][Nasdaq.Phlx.Orders.Itch.v1.9.Dissector] | 8/10/2015 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nasdaq][Nasdaq.Directory] | Phlx | [Topo][Nasdaq.Phlx.Topo.Itch.v3.3.Dissector] | Itch | [3.3][Nasdaq.Phlx.Topo.Itch.v3.3.Dissector] | 11/2/2017 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nasdaq][Nasdaq.Directory] | Psx | [Bbo][Nasdaq.Psx.Bbo.Itch.v2.1.Dissector] | Itch | [2.1][Nasdaq.Psx.Bbo.Itch.v2.1.Dissector] | 5/3/2018 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nasdaq][Nasdaq.Directory] | Psx | [LastSale][Nasdaq.Psx.LastSale.Itch.v2.1.Dissector] | Itch | [2.1][Nasdaq.Psx.LastSale.Itch.v2.1.Dissector] | 5/3/2018 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nasdaq][Nasdaq.Directory] | Psx | [TotalView][Nasdaq.Psx.TotalView.Itch.v5.0.Dissector] | Itch | [5.0][Nasdaq.Psx.TotalView.Itch.v5.0.Dissector] | 5/3/2018 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nasdaq][Nasdaq.Directory] | Psx | [Orders][Nasdaq.Psx.Orders.Ouch.v4.2.Dissector] | Ouch | [4.2][Nasdaq.Psx.Orders.Ouch.v4.2.Dissector] | 7/8/2019 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nasdaq][Nasdaq.Directory] | Uqdf | [Output][Nasdaq.Uqdf.Output.Utp.v1.5.Dissector] | Utp | [1.5][Nasdaq.Uqdf.Output.Utp.v1.5.Dissector] | 5/1/2020 | [Verified][Omi.Glossary.Testing.Verified] |
| [Nasdaq][Nasdaq.Directory] | Utdf | [Output][Nasdaq.Utdf.Output.Utp.v1.5.Dissector] | Utp | [1.5][Nasdaq.Utdf.Output.Utp.v1.5.Dissector] | 5/1/2020 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nyse][Nyse.Directory] |  Equities | [OpenBook][Nyse.Equities.OpenBook.Ultra.v2.1.b.Dissector] | Ultra | [2.1.b][Nyse.Equities.OpenBook.Ultra.v2.1.b.Dissector] | 3/9/2018 | [Verified][Omi.Glossary.Testing.Verified] |
| [Nyse][Nyse.Directory] | Amex Equities | [OpenBook][Nyse.Amex.Equities.OpenBook.Ultra.v2.1.b.Dissector] | Ultra | [2.1.b][Nyse.Amex.Equities.OpenBook.Ultra.v2.1.b.Dissector] | 3/9/2018 | [Verified][Omi.Glossary.Testing.Verified] |
| [Nyse][Nyse.Directory] | Amex Equities | [IntegratedFeed][Nyse.Amex.Equities.IntegratedFeed.Xdp.v2.1.g.Dissector] | Xdp | [2.1.g][Nyse.Amex.Equities.IntegratedFeed.Xdp.v2.1.g.Dissector] | 1/29/2018 | [Verified][Omi.Glossary.Testing.Verified] |
| [Nyse][Nyse.Directory] | Arca Equities | [Bbo][Nyse.Arca.Equities.Bbo.Xdp.v2.4.c.Dissector] | Xdp | [2.4.c][Nyse.Arca.Equities.Bbo.Xdp.v2.4.c.Dissector] | 7/13/2016 | [Verified][Omi.Glossary.Testing.Verified] |
| [Nyse][Nyse.Directory] | Equities | [Bbo][Nyse.Equities.Bbo.Xdp.v2.4.g.Dissector] | Xdp | [2.4.g][Nyse.Equities.Bbo.Xdp.v2.4.g.Dissector] | 1/29/2018 | [Verified][Omi.Glossary.Testing.Verified] |
| [Nyse][Nyse.Directory] | Equities | [Bqt][Nyse.Equities.Bqt.Xdp.v2.1.a.Dissector] | Xdp | [2.1.a][Nyse.Equities.Bqt.Xdp.v2.1.a.Dissector] | 4/4/2018 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nyse][Nyse.Directory] | Equities | [Bqt][Nyse.Equities.Bqt.Xdp.v1.7.a.Dissector] | Xdp | [1.7.a][Nyse.Equities.Bqt.Xdp.v1.7.a.Dissector] | 7/24/2017 | [Verified][Omi.Glossary.Testing.Verified] |
| [Nyse][Nyse.Directory] | Equities | [ImbalancesFeed][Nyse.Equities.ImbalancesFeed.Xdp.v2.2.a.Dissector] | Xdp | [2.2.a][Nyse.Equities.ImbalancesFeed.Xdp.v2.2.a.Dissector] | 3/8/2019 | [Verified][Omi.Glossary.Testing.Verified] |
| [Nyse][Nyse.Directory] | Equities | [IntegratedFeed][Nyse.Equities.IntegratedFeed.Xdp.v2.1.g.Dissector] | Xdp | [2.1.g][Nyse.Equities.IntegratedFeed.Xdp.v2.1.g.Dissector] | 1/29/2018 | [Verified][Omi.Glossary.Testing.Verified] |
| [Nyse][Nyse.Directory] | Options | [ComplexFeed][Nyse.Options.ComplexFeed.Xdp.v1.3.a.Dissector] | Xdp | [1.3.a][Nyse.Options.ComplexFeed.Xdp.v1.3.a.Dissector] | 2/28/2018 | [Verified][Omi.Glossary.Testing.Verified] |
| [Nyse][Nyse.Directory] | Options | [DeepFeed][Nyse.Options.DeepFeed.Xdp.v1.3.a.Dissector] | Xdp | [1.3.a][Nyse.Options.DeepFeed.Xdp.v1.3.a.Dissector] | 2/28/2018 | [Untested][Omi.Glossary.Testing.Untested] |
| [Nyse][Nyse.Directory] | Options | [TopFeed][Nyse.Options.TopFeed.Xdp.v1.3.a.Dissector] | Xdp | [1.3.a][Nyse.Options.TopFeed.Xdp.v1.3.a.Dissector] | 2/28/2018 | [Untested][Omi.Glossary.Testing.Untested] |
| [Otc][Otc.Directory] | Markets | [Headers][Otc.Markets.Headers.Ats.v1.0.Dissector] | Ats | [1.0][Otc.Markets.Headers.Ats.v1.0.Dissector] | 12/11/2019 | [Verified][Omi.Glossary.Testing.Verified] |
| [Otc][Otc.Directory] | Markets | [Multicast][Otc.Markets.Multicast.Ats.v4.3.Dissector] | Ats | [4.3][Otc.Markets.Multicast.Ats.v4.3.Dissector] | 12/11/2019 | [Verified][Omi.Glossary.Testing.Verified] |
| [Siac][Siac.Directory] | Cqs | [Output][Siac.Cqs.Output.Cta.v1.91.Dissector] | Cta | [1.91][Siac.Cqs.Output.Cta.v1.91.Dissector] | 1/2/2020 | [Verified][Omi.Glossary.Testing.Verified] |
| [Siac][Siac.Directory] | Cts | [Output][Siac.Cts.Output.Cta.v1.91.Dissector] | Cta | [1.91][Siac.Cts.Output.Cta.v1.91.Dissector] | 1/2/2020 | [Beta][Omi.Glossary.Testing.Beta] |
| [Siac][Siac.Directory] | Opra | [Recipient][Siac.Opra.Recipient.Obi.v4.0.Dissector] | Obi | [4.0][Siac.Opra.Recipient.Obi.v4.0.Dissector] | 1/17/2020 | [Untested][Omi.Glossary.Testing.Untested] |

Obsolete and header dissectors are in dissector directories: [Asx][Asx.Directory], [Cboe][Cboe.Directory], [Cme][Cme.Directory], [Eurex][Eurex.Directory], [Euronext][Euronext.Directory], [Finra][Finra.Directory], [Ice][Ice.Directory], [Iex][Iex.Directory], [Lse][Lse.Directory], [Miax][Miax.Directory], [Memx][Memx.Directory], [Nasdaq][Nasdaq.Directory], [Nyse][Nyse.Directory], [Otc][Otc.Directory], [Siac][Siac.Directory]

## Development

Updates are greatly appreciated; however, this entire repository is source generated...including the words you are reading right now. If you wish to suggest script updates, the recommended process is to create an issue with changes and explanation.  Time permitting, we will update the models and regenerate.

| Protocol Count | Generated Lines |
| --- | --- |
| 130 | 1,115,506 |

Note: Our dissector model is still under rapid development.

## Testing

Please report any dissection errors as issues.  Include a small note on the protocol and version, and a minimal capture demonstrating the problem. Also consider including a link or pdf specification documenting the correct behavior.

Production packet captures are required for protocol verification.  If your organization has the rights to packet captures, and you wish to make the world a better place, please post captures to this project.

List of data requests: [Untested Protocols](https://github.com/Open-Markets-Initiative/wireshark-lua/wiki/Data "Unverified Protocol Data List")
## Open Markets Initiative

The Open Markets Initiative (Omi) is a group of technologists dedicated to enhancing the stability of electronic financial markets using modern development methods.

For a list of Omi Hft projects: [Omi Projects](https://github.com/Open-Markets-Initiative/Directory/tree/master/Projects "Open Markets Initiative Projects")

For details of Omi rules and regulations: [Omi Directory](https://github.com/Open-Markets-Initiative/Directory "Open Markets Initiative Directory")
## Disclaimer

Any similarities between existing people, places and/or protocols is purely incidental.

Enjoy.

[Omi Projects]: https://github.com/Open-Markets-Initiative/Directory/tree/master/Projects "Open Markets Initiative Projects"
[Omi Rules and Regulations]: https://github.com/Open-Markets-Initiative/Directory/tree/master/License "Open Markets Initiative Rules and Regulations"

[Omi.Glossary.Testing]: https://github.com/Open-Markets-Initiative/Directory/blob/master/Glossary/Testing.md "Protocol Testing Status"
[Omi.Glossary.Testing.Verified]: https://github.com/Open-Markets-Initiative/Directory/blob/master/Glossary/Testing.md "Testing Status: Protocol has been tested on live data"
[Omi.Glossary.Testing.Incomplete]: https://github.com/Open-Markets-Initiative/Directory/blob/master/Glossary/Testing.md "Testing Status: Protocol has been tested on live data but contains known issues"
[Omi.Glossary.Testing.Beta]: https://github.com/Open-Markets-Initiative/Directory/blob/master/Glossary/Testing.md "Testing Status: Protocol has not been tested and structure is speculative"
[Omi.Glossary.Testing.Untested]: https://github.com/Open-Markets-Initiative/Directory/blob/master/Glossary/Testing.md "Testing Status: Protocol has not been tested on live data"

[Asx.Directory]: https://github.com/Open-Markets-Initiative/wireshark-lua/tree/master/Asx "Australian Securities Exchange"
[Cboe.Directory]: https://github.com/Open-Markets-Initiative/wireshark-lua/tree/master/Cboe "Chicago Board Options Exchange"
[Cme.Directory]: https://github.com/Open-Markets-Initiative/wireshark-lua/tree/master/Cme "Chicago Mercantile Exchange"
[Eurex.Directory]: https://github.com/Open-Markets-Initiative/wireshark-lua/tree/master/Eurex "Eurex Exchange"
[Euronext.Directory]: https://github.com/Open-Markets-Initiative/wireshark-lua/tree/master/Euronext "European New Exchange Technology"
[Finra.Directory]: https://github.com/Open-Markets-Initiative/wireshark-lua/tree/master/Finra "Financial Industry Regulatory Authority"
[Ice.Directory]: https://github.com/Open-Markets-Initiative/wireshark-lua/tree/master/Ice "Intercontinental Exchange"
[Iex.Directory]: https://github.com/Open-Markets-Initiative/wireshark-lua/tree/master/Iex "Investors Exchange"
[Lse.Directory]: https://github.com/Open-Markets-Initiative/wireshark-lua/tree/master/Lse "London Stock Exchange"
[Miax.Directory]: https://github.com/Open-Markets-Initiative/wireshark-lua/tree/master/Miax "Miami International Securities Exchange"
[Memx.Directory]: https://github.com/Open-Markets-Initiative/wireshark-lua/tree/master/Memx "Members Exchange"
[Nasdaq.Directory]: https://github.com/Open-Markets-Initiative/wireshark-lua/tree/master/Nasdaq "National Association of Securities Dealers Automated Quotations"
[Nyse.Directory]: https://github.com/Open-Markets-Initiative/wireshark-lua/tree/master/Nyse "New York Stock Exchange"
[Otc.Directory]: https://github.com/Open-Markets-Initiative/wireshark-lua/tree/master/Otc "Otc Markets"
[Siac.Directory]: https://github.com/Open-Markets-Initiative/wireshark-lua/tree/master/Siac "Securities Industry Automation Corporation"

[Asx.Securities.Ntp.Itch.v1.05.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Asx/Asx.Securities.Ntp.Itch.v1.05.Script.Dissector.lua "Asx Securities Ntp Itch v1.05 Lua Wireshark Dissector"
[Cboe.Bzx.Equities.OrderEntry.Boe.v2.3.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Cboe/Cboe.Bzx.Equities.OrderEntry.Boe.v2.3.Script.Dissector.lua "Cboe Bzx Equities OrderEntry Boe v2.3 Lua Wireshark Dissector"
[Cboe.Edgx.Equities.OrderEntry.Boe.v2.3.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Cboe/Cboe.Edgx.Equities.OrderEntry.Boe.v2.3.Script.Dissector.lua "Cboe Edgx Equities OrderEntry Boe v2.3 Lua Wireshark Dissector"
[Cboe.Futures.DepthOfBook.Pitch.v1.1.12.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Cboe/Cboe.Futures.DepthOfBook.Pitch.v1.1.12.Script.Dissector.lua "Cboe Futures DepthOfBook Pitch v1.1.12 Lua Wireshark Dissector"
[Cboe.Futures.OrderEntry.Boe.v1.3.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Cboe/Cboe.Futures.OrderEntry.Boe.v1.3.Script.Dissector.lua "Cboe Futures OrderEntry Boe v1.3 Lua Wireshark Dissector"
[Cboe.Options.ComplexDepthOfBook.Pitch.v2.1.18.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Cboe/Cboe.Options.ComplexDepthOfBook.Pitch.v2.1.18.Script.Dissector.lua "Cboe Options ComplexDepthOfBook Pitch v2.1.18 Lua Wireshark Dissector"
[Cboe.Bzx.Options.OrderEntry.Boe.v2.10.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Cboe/Cboe.Bzx.Options.OrderEntry.Boe.v2.10.Script.Dissector.lua "Cboe Bzx Options OrderEntry Boe v2.10 Lua Wireshark Dissector"
[Cboe.C1.Options.AuctionFeed.Pitch.v1.1.1.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Cboe/Cboe.C1.Options.AuctionFeed.Pitch.v1.1.1.Script.Dissector.lua "Cboe C1 Options AuctionFeed Pitch v1.1.1 Lua Wireshark Dissector"
[Cboe.C1.Options.OrderEntry.Boe.v2.10.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Cboe/Cboe.C1.Options.OrderEntry.Boe.v2.10.Script.Dissector.lua "Cboe C1 Options OrderEntry Boe v2.10 Lua Wireshark Dissector"
[Cboe.Edgx.Options.AuctionFeed.Pitch.v1.1.1.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Cboe/Cboe.Edgx.Options.AuctionFeed.Pitch.v1.1.1.Script.Dissector.lua "Cboe Edgx Options AuctionFeed Pitch v1.1.1 Lua Wireshark Dissector"
[Cboe.Edgx.Options.OrderEntry.Boe.v2.10.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Cboe/Cboe.Edgx.Options.OrderEntry.Boe.v2.10.Script.Dissector.lua "Cboe Edgx Options OrderEntry Boe v2.10 Lua Wireshark Dissector"
[Cboe.Options.DepthOfBook.Pitch.v2.39.4.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Cboe/Cboe.Options.DepthOfBook.Pitch.v2.39.4.Script.Dissector.lua "Cboe Options DepthOfBook Pitch v2.39.4 Lua Wireshark Dissector"
[Cme.Futures.Mdp3.Sbe.v1.11.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Cme/Cme.Futures.Mdp3.Sbe.v1.11.Script.Dissector.lua "Cme Futures Mdp3 Sbe v1.11 Lua Wireshark Dissector"
[Cme.Futures.Streamline.Sbe.v5.9.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Cme/Cme.Futures.Streamline.Sbe.v5.9.Script.Dissector.lua "Cme Futures Streamline Sbe v5.9 Lua Wireshark Dissector"
[Cme.Futures.Settlements.Sbe.v7.0.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Cme/Cme.Futures.Settlements.Sbe.v7.0.Script.Dissector.lua "Cme Futures Settlements Sbe v7.0 Lua Wireshark Dissector"
[Cme.Futures.iLink3.Sbe.v8.7.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Cme/Cme.Futures.iLink3.Sbe.v8.7.Script.Dissector.lua "Cme Futures iLink3 Sbe v8.7 Lua Wireshark Dissector"
[Eurex.Cash.Eti.T7.v9.0.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Eurex/Eurex.Cash.Eti.T7.v9.0.Script.Dissector.lua "Eurex Cash Eti T7 v9.0 Lua Wireshark Dissector"
[Eurex.Derivatives.Eti.T7.v9.0.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Eurex/Eurex.Derivatives.Eti.T7.v9.0.Script.Dissector.lua "Eurex Derivatives Eti T7 v9.0 Lua Wireshark Dissector"
[Eurex.Derivatives.Eobi.T7.v9.0.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Eurex/Eurex.Derivatives.Eobi.T7.v9.0.Script.Dissector.lua "Eurex Derivatives Eobi T7 v9.0 Lua Wireshark Dissector"
[Euronext.Optiq.OrderEntryGateway.Sbe.v4.2.2.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Euronext/Euronext.Optiq.OrderEntryGateway.Sbe.v4.2.2.Script.Dissector.lua "Euronext Optiq OrderEntryGateway Sbe v4.2.2 Lua Wireshark Dissector"
[Euronext.Optiq.MarketDataGateway.Sbe.v4.3.0.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Euronext/Euronext.Optiq.MarketDataGateway.Sbe.v4.3.0.Script.Dissector.lua "Euronext Optiq MarketDataGateway Sbe v4.3.0 Lua Wireshark Dissector"
[Finra.Orf.Tdds.Dfi.v2.0.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Finra/Finra.Orf.Tdds.Dfi.v2.0.Script.Dissector.lua "Finra Orf Tdds Dfi v2.0 Lua Wireshark Dissector"
[Finra.Otc.Bbds.Dfi.v2018.1A.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Finra/Finra.Otc.Bbds.Dfi.v2018.1A.Script.Dissector.lua "Finra Otc Bbds Dfi v2018.1A Lua Wireshark Dissector"
[Ice.Futures.Mdf.iMpact.v1.1.34.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Ice/Ice.Futures.Mdf.iMpact.v1.1.34.Script.Dissector.lua "Ice Futures Mdf iMpact v1.1.34 Lua Wireshark Dissector"
[Iex.Equities.Deep.IexTp.v1.0.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Iex/Iex.Equities.Deep.IexTp.v1.0.Script.Dissector.lua "Iex Equities Deep IexTp v1.0 Lua Wireshark Dissector"
[Iex.Equities.Tops.IexTp.v1.6.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Iex/Iex.Equities.Tops.IexTp.v1.6.Script.Dissector.lua "Iex Equities Tops IexTp v1.6 Lua Wireshark Dissector"
[Lse.Millennium.Level2.Mitch.v11.9.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Lse/Lse.Millennium.Level2.Mitch.v11.9.Script.Dissector.lua "Lse Millennium Level2 Mitch v11.9 Lua Wireshark Dissector"
[Miax.Options.ComplexTopOfMarket.Mach.v1.3.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Miax/Miax.Options.ComplexTopOfMarket.Mach.v1.3.Script.Dissector.lua "Miax Options ComplexTopOfMarket Mach v1.3 Lua Wireshark Dissector"
[Miax.Options.TopOfMarket.Mach.v2.2.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Miax/Miax.Options.TopOfMarket.Mach.v2.2.Script.Dissector.lua "Miax Options TopOfMarket Mach v2.2 Lua Wireshark Dissector"
[Miax.Options.TopOfMarket.Mach.v2.3.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Miax/Miax.Options.TopOfMarket.Mach.v2.3.Script.Dissector.lua "Miax Options TopOfMarket Mach v2.3 Lua Wireshark Dissector"
[Miax.Pearl.Equities.DepthOfMarket.Mach.v1.3.a.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Miax/Miax.Pearl.Equities.DepthOfMarket.Mach.v1.3.a.Script.Dissector.lua "Miax Pearl Equities DepthOfMarket Mach v1.3.a Lua Wireshark Dissector"
[Miax.Pearl.Equities.TopOfMarket.Mach.v1.1.a.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Miax/Miax.Pearl.Equities.TopOfMarket.Mach.v1.1.a.Script.Dissector.lua "Miax Pearl Equities TopOfMarket Mach v1.1.a Lua Wireshark Dissector"
[Miax.Pearl.Options.TopOfMarket.Mach.v1.0.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Miax/Miax.Pearl.Options.TopOfMarket.Mach.v1.0.Script.Dissector.lua "Miax Pearl Options TopOfMarket Mach v1.0 Lua Wireshark Dissector"
[Memx.Equities.MemoirDepthFeed.Sbe.v1.1.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Memx/Memx.Equities.MemoirDepthFeed.Sbe.v1.1.Script.Dissector.lua "Memx Equities MemoirDepthFeed Sbe v1.1 Lua Wireshark Dissector"
[Memx.Equities.MemoirLastSale.Sbe.v1.1.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Memx/Memx.Equities.MemoirLastSale.Sbe.v1.1.Script.Dissector.lua "Memx Equities MemoirLastSale Sbe v1.1 Lua Wireshark Dissector"
[Memx.Equities.MemoirTopOfBook.Sbe.v1.1.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Memx/Memx.Equities.MemoirTopOfBook.Sbe.v1.1.Script.Dissector.lua "Memx Equities MemoirTopOfBook Sbe v1.1 Lua Wireshark Dissector"
[Memx.Equities.Memo.Sbe.v1.1.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Memx/Memx.Equities.Memo.Sbe.v1.1.Script.Dissector.lua "Memx Equities Memo Sbe v1.1 Lua Wireshark Dissector"
[Memx.Equities.Memo.Sbe.v1.2.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Memx/Memx.Equities.Memo.Sbe.v1.2.Script.Dissector.lua "Memx Equities Memo Sbe v1.2 Lua Wireshark Dissector"
[Nasdaq.Bx.Equities.TotalView.Itch.v5.0.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Bx.Equities.TotalView.Itch.v5.0.Script.Dissector.lua "Nasdaq Bx Equities TotalView Itch v5.0 Lua Wireshark Dissector"
[Nasdaq.Bx.Equities.Orders.Ouch.v4.2.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Bx.Equities.Orders.Ouch.v4.2.Script.Dissector.lua "Nasdaq Bx Equities Orders Ouch v4.2 Lua Wireshark Dissector"
[Nasdaq.Bx.Options.TopOfMarket.Itch.v1.2.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Bx.Options.TopOfMarket.Itch.v1.2.Script.Dissector.lua "Nasdaq Bx Options TopOfMarket Itch v1.2 Lua Wireshark Dissector"
[Nasdaq.Bx.Options.DepthOfMarket.Itch.v1.3.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Bx.Options.DepthOfMarket.Itch.v1.3.Script.Dissector.lua "Nasdaq Bx Options DepthOfMarket Itch v1.3 Lua Wireshark Dissector"
[Nasdaq.Ise.OrderComboFeed.Itch.v1.1.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Ise.OrderComboFeed.Itch.v1.1.Script.Dissector.lua "Nasdaq Ise OrderComboFeed Itch v1.1 Lua Wireshark Dissector"
[Nasdaq.Ise.OrderFeed.Itch.v1.1.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Ise.OrderFeed.Itch.v1.1.Script.Dissector.lua "Nasdaq Ise OrderFeed Itch v1.1 Lua Wireshark Dissector"
[Nasdaq.Ise.TopComboQuoteFeed.Itch.v1.0.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Ise.TopComboQuoteFeed.Itch.v1.0.Script.Dissector.lua "Nasdaq Ise TopComboQuoteFeed Itch v1.0 Lua Wireshark Dissector"
[Nasdaq.Nom.Bono.Itch.v3.2.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Nom.Bono.Itch.v3.2.Script.Dissector.lua "Nasdaq Nom Bono Itch v3.2 Lua Wireshark Dissector"
[Nasdaq.Nom.Itto.Itch.v4.0.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Nom.Itto.Itch.v4.0.Script.Dissector.lua "Nasdaq Nom Itto Itch v4.0 Lua Wireshark Dissector"
[Nasdaq.Phlx.MarketDepth.Itch.v1.6.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Phlx.MarketDepth.Itch.v1.6.Script.Dissector.lua "Nasdaq Phlx MarketDepth Itch v1.6 Lua Wireshark Dissector"
[Nasdaq.Phlx.Orders.Itch.v1.9.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Phlx.Orders.Itch.v1.9.Script.Dissector.lua "Nasdaq Phlx Orders Itch v1.9 Lua Wireshark Dissector"
[Nasdaq.Phlx.Topo.Itch.v3.3.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Phlx.Topo.Itch.v3.3.Script.Dissector.lua "Nasdaq Phlx Topo Itch v3.3 Lua Wireshark Dissector"
[Nasdaq.Psx.LastSale.Itch.v2.1.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Psx.LastSale.Itch.v2.1.Script.Dissector.lua "Nasdaq Psx LastSale Itch v2.1 Lua Wireshark Dissector"
[Nasdaq.Psx.TotalView.Itch.v5.0.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Psx.TotalView.Itch.v5.0.Script.Dissector.lua "Nasdaq Psx TotalView Itch v5.0 Lua Wireshark Dissector"
[Nasdaq.Psx.Bbo.Itch.v2.1.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Psx.Bbo.Itch.v2.1.Script.Dissector.lua "Nasdaq Psx Bbo Itch v2.1 Lua Wireshark Dissector"
[Nasdaq.Psx.Orders.Ouch.v4.2.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Psx.Orders.Ouch.v4.2.Script.Dissector.lua "Nasdaq Psx Orders Ouch v4.2 Lua Wireshark Dissector"
[Nasdaq.Equities.Aggregated.Itch.v2.0.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Equities.Aggregated.Itch.v2.0.Script.Dissector.lua "Nasdaq Equities Aggregated Itch v2.0 Lua Wireshark Dissector"
[Nasdaq.Equities.Level2.Itch.v2.0.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Equities.Level2.Itch.v2.0.Script.Dissector.lua "Nasdaq Equities Level2 Itch v2.0 Lua Wireshark Dissector"
[Nasdaq.Equities.Noi.Itch.v3.0.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Equities.Noi.Itch.v3.0.Script.Dissector.lua "Nasdaq Equities Noi Itch v3.0 Lua Wireshark Dissector"
[Nasdaq.Equities.Orders.Ouch.v4.2.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Equities.Orders.Ouch.v4.2.Script.Dissector.lua "Nasdaq Equities Orders Ouch v4.2 Lua Wireshark Dissector"
[Nasdaq.Equities.TotalView.Itch.v5.0.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Equities.TotalView.Itch.v5.0.Script.Dissector.lua "Nasdaq Equities TotalView Itch v5.0 Lua Wireshark Dissector"
[Nasdaq.Uqdf.Output.Utp.v1.5.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Uqdf.Output.Utp.v1.5.Script.Dissector.lua "Nasdaq Uqdf Output Utp v1.5 Lua Wireshark Dissector"
[Nasdaq.Utdf.Output.Utp.v1.5.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nasdaq/Nasdaq.Utdf.Output.Utp.v1.5.Script.Dissector.lua "Nasdaq Utdf Output Utp v1.5 Lua Wireshark Dissector"
[Nyse.Amex.Equities.OpenBook.Ultra.v2.1.b.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nyse/Nyse.Amex.Equities.OpenBook.Ultra.v2.1.b.Script.Dissector.lua "Nyse Amex Equities OpenBook Ultra v2.1.b Lua Wireshark Dissector"
[Nyse.Equities.OpenBook.Ultra.v2.1.b.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nyse/Nyse.Equities.OpenBook.Ultra.v2.1.b.Script.Dissector.lua "Nyse Equities OpenBook Ultra v2.1.b Lua Wireshark Dissector"
[Nyse.Amex.Equities.IntegratedFeed.Xdp.v2.1.g.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nyse/Nyse.Amex.Equities.IntegratedFeed.Xdp.v2.1.g.Script.Dissector.lua "Nyse Amex Equities IntegratedFeed Xdp v2.1.g Lua Wireshark Dissector"
[Nyse.Arca.Equities.Bbo.Xdp.v2.4.c.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nyse/Nyse.Arca.Equities.Bbo.Xdp.v2.4.c.Script.Dissector.lua "Nyse Arca Equities Bbo Xdp v2.4.c Lua Wireshark Dissector"
[Nyse.Equities.Bbo.Xdp.v2.4.g.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nyse/Nyse.Equities.Bbo.Xdp.v2.4.g.Script.Dissector.lua "Nyse Equities Bbo Xdp v2.4.g Lua Wireshark Dissector"
[Nyse.Equities.Bqt.Xdp.v1.7.a.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nyse/Nyse.Equities.Bqt.Xdp.v1.7.a.Script.Dissector.lua "Nyse Equities Bqt Xdp v1.7.a Lua Wireshark Dissector"
[Nyse.Equities.Bqt.Xdp.v2.1.a.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nyse/Nyse.Equities.Bqt.Xdp.v2.1.a.Script.Dissector.lua "Nyse Equities Bqt Xdp v2.1.a Lua Wireshark Dissector"
[Nyse.Equities.ImbalancesFeed.Xdp.v2.2.a.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nyse/Nyse.Equities.ImbalancesFeed.Xdp.v2.2.a.Script.Dissector.lua "Nyse Equities ImbalancesFeed Xdp v2.2.a Lua Wireshark Dissector"
[Nyse.Equities.IntegratedFeed.Xdp.v2.1.g.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nyse/Nyse.Equities.IntegratedFeed.Xdp.v2.1.g.Script.Dissector.lua "Nyse Equities IntegratedFeed Xdp v2.1.g Lua Wireshark Dissector"
[Nyse.Options.ComplexFeed.Xdp.v1.3.a.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nyse/Nyse.Options.ComplexFeed.Xdp.v1.3.a.Script.Dissector.lua "Nyse Options ComplexFeed Xdp v1.3.a Lua Wireshark Dissector"
[Nyse.Options.DeepFeed.Xdp.v1.3.a.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nyse/Nyse.Options.DeepFeed.Xdp.v1.3.a.Script.Dissector.lua "Nyse Options DeepFeed Xdp v1.3.a Lua Wireshark Dissector"
[Nyse.Options.TopFeed.Xdp.v1.3.a.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Nyse/Nyse.Options.TopFeed.Xdp.v1.3.a.Script.Dissector.lua "Nyse Options TopFeed Xdp v1.3.a Lua Wireshark Dissector"
[Otc.Markets.Headers.Ats.v1.0.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Otc/Otc.Markets.Headers.Ats.v1.0.Script.Dissector.lua "Otc Markets Headers Ats v1.0 Lua Wireshark Dissector"
[Otc.Markets.Multicast.Ats.v4.3.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Otc/Otc.Markets.Multicast.Ats.v4.3.Script.Dissector.lua "Otc Markets Multicast Ats v4.3 Lua Wireshark Dissector"
[Siac.Opra.Recipient.Obi.v4.0.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Siac/Siac.Opra.Recipient.Obi.v4.0.Script.Dissector.lua "Siac Opra Recipient Obi v4.0 Lua Wireshark Dissector"
[Siac.Cqs.Output.Cta.v1.91.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Siac/Siac.Cqs.Output.Cta.v1.91.Script.Dissector.lua "Siac Cqs Output Cta v1.91 Lua Wireshark Dissector"
[Siac.Cts.Output.Cta.v1.91.Dissector]: https://github.com/Open-Markets-Initiative/wireshark-lua/blob/master/Siac/Siac.Cts.Output.Cta.v1.91.Script.Dissector.lua "Siac Cts Output Cta v1.91 Lua Wireshark Dissector"
