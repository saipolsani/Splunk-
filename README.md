# Splunk-
Visualization of corona virus data using Splunk

<form theme="dark">
  <label>Corona</label>
  <fieldset submitButton="true" autoRun="false">
    <input type="dropdown" token="country">
      <label>country</label>
      <fieldForLabel>Country_Region</fieldForLabel>
      <fieldForValue>Country_Region</fieldForValue>
      <search>
        <query>index="corona" source="2019_nCoV_20200121_20200127.csv" | stats  count by Country_Region | table Country_Region</query>
        <earliest>0</earliest>
        <latest></latest>
      </search>
    </input>
  </fieldset>
  <row>
    <panel>
      <title>Total_Suspected</title>
      <single>
        <search>
          <query>index="corona" source="2019_nCoV_20200121_20200127.csv" Country_Region = "$country$" |  stats sum(Suspected) as Total_Suspected</query>
          <earliest>0</earliest>
          <sampleRatio>1</sampleRatio>
        </search>
        <option name="colorBy">value</option>
        <option name="colorMode">none</option>
        <option name="drilldown">none</option>
        <option name="numberPrecision">0</option>
        <option name="rangeColors">["0x53a051", "0x0877a6", "0xf8be34", "0xf1813f", "0xdc4e41"]</option>
        <option name="rangeValues">[0,30,70,100]</option>
        <option name="showSparkline">1</option>
        <option name="showTrendIndicator">1</option>
        <option name="trellis.enabled">0</option>
        <option name="trellis.scales.shared">1</option>
        <option name="trellis.size">medium</option>
        <option name="trendColorInterpretation">standard</option>
        <option name="trendDisplayMode">absolute</option>
        <option name="unitPosition">after</option>
        <option name="useColors">0</option>
        <option name="useThousandSeparators">1</option>
      </single>
    </panel>
    <panel>
      <title>Total Recovered</title>
      <single>
        <search>
          <query>index="corona" source="2019_nCoV_20200121_20200127.csv" Country_Region = "$country$" |stats sum(Recovered) as Total_Recovered</query>
          <earliest>0</earliest>
          <sampleRatio>1</sampleRatio>
        </search>
        <option name="colorBy">value</option>
        <option name="colorMode">none</option>
        <option name="drilldown">none</option>
        <option name="numberPrecision">0</option>
        <option name="rangeColors">["0x53a051", "0x0877a6", "0xf8be34", "0xf1813f", "0xdc4e41"]</option>
        <option name="rangeValues">[0,30,70,100]</option>
        <option name="showSparkline">1</option>
        <option name="showTrendIndicator">1</option>
        <option name="trellis.enabled">0</option>
        <option name="trellis.scales.shared">1</option>
        <option name="trellis.size">medium</option>
        <option name="trendColorInterpretation">standard</option>
        <option name="trendDisplayMode">absolute</option>
        <option name="unitPosition">after</option>
        <option name="useColors">0</option>
        <option name="useThousandSeparators">1</option>
      </single>
    </panel>
  </row>
  <row>
    <panel>
      <title>Total_Sus_China_timechart</title>
      <chart>
        <search>
          <query>index="corona" source="2019_nCoV_20200121_20200127.csv" Country_Region = "$country$"  |timechart  sum(Suspected) as Total_Suspected</query>
          <earliest>0</earliest>
          <sampleRatio>1</sampleRatio>
        </search>
        <option name="charting.axisLabelsX.majorLabelStyle.overflowMode">ellipsisNone</option>
        <option name="charting.axisLabelsX.majorLabelStyle.rotation">0</option>
        <option name="charting.axisTitleX.visibility">visible</option>
        <option name="charting.axisTitleY.visibility">visible</option>
        <option name="charting.axisTitleY2.visibility">visible</option>
        <option name="charting.axisX.abbreviation">none</option>
        <option name="charting.axisX.scale">linear</option>
        <option name="charting.axisY.abbreviation">none</option>
        <option name="charting.axisY.scale">linear</option>
        <option name="charting.axisY2.abbreviation">none</option>
        <option name="charting.axisY2.enabled">0</option>
        <option name="charting.axisY2.scale">inherit</option>
        <option name="charting.chart">column</option>
        <option name="charting.chart.bubbleMaximumSize">50</option>
        <option name="charting.chart.bubbleMinimumSize">10</option>
        <option name="charting.chart.bubbleSizeBy">area</option>
        <option name="charting.chart.nullValueMode">gaps</option>
        <option name="charting.chart.showDataLabels">none</option>
        <option name="charting.chart.sliceCollapsingThreshold">0.01</option>
        <option name="charting.chart.stackMode">default</option>
        <option name="charting.chart.style">shiny</option>
        <option name="charting.drilldown">none</option>
        <option name="charting.layout.splitSeries">0</option>
        <option name="charting.layout.splitSeries.allowIndependentYRanges">0</option>
        <option name="charting.legend.labelStyle.overflowMode">ellipsisMiddle</option>
        <option name="charting.legend.mode">standard</option>
        <option name="charting.legend.placement">right</option>
        <option name="charting.lineWidth">2</option>
        <option name="trellis.enabled">0</option>
        <option name="trellis.scales.shared">1</option>
        <option name="trellis.size">medium</option>
      </chart>
    </panel>
    <panel>
      <title>Total Recovered over time</title>
      <chart>
        <search>
          <query>index="corona" source="2019_nCoV_20200121_20200127.csv" Country_Region = "$country$" |timechart sum(Recovered) as Total_Recovered</query>
          <earliest>0</earliest>
          <sampleRatio>1</sampleRatio>
        </search>
        <option name="charting.axisLabelsX.majorLabelStyle.overflowMode">ellipsisNone</option>
        <option name="charting.axisLabelsX.majorLabelStyle.rotation">0</option>
        <option name="charting.axisTitleX.visibility">visible</option>
        <option name="charting.axisTitleY.visibility">visible</option>
        <option name="charting.axisTitleY2.visibility">visible</option>
        <option name="charting.axisX.abbreviation">none</option>
        <option name="charting.axisX.scale">linear</option>
        <option name="charting.axisY.abbreviation">none</option>
        <option name="charting.axisY.scale">linear</option>
        <option name="charting.axisY2.abbreviation">none</option>
        <option name="charting.axisY2.enabled">0</option>
        <option name="charting.axisY2.scale">inherit</option>
        <option name="charting.chart">column</option>
        <option name="charting.chart.bubbleMaximumSize">50</option>
        <option name="charting.chart.bubbleMinimumSize">10</option>
        <option name="charting.chart.bubbleSizeBy">area</option>
        <option name="charting.chart.nullValueMode">gaps</option>
        <option name="charting.chart.showDataLabels">none</option>
        <option name="charting.chart.sliceCollapsingThreshold">0.01</option>
        <option name="charting.chart.stackMode">default</option>
        <option name="charting.chart.style">shiny</option>
        <option name="charting.drilldown">none</option>
        <option name="charting.layout.splitSeries">0</option>
        <option name="charting.layout.splitSeries.allowIndependentYRanges">0</option>
        <option name="charting.legend.labelStyle.overflowMode">ellipsisMiddle</option>
        <option name="charting.legend.mode">standard</option>
        <option name="charting.legend.placement">right</option>
        <option name="charting.lineWidth">2</option>
        <option name="trellis.enabled">0</option>
        <option name="trellis.scales.shared">1</option>
        <option name="trellis.size">medium</option>
      </chart>
    </panel>
  </row>
  <row>
    <panel>
      <title>Total confirmed cases over time</title>
      <chart>
        <search>
          <query>index="corona" source="2019_ncov_20200121_20200127.csv" Country_Region = "$country$" | timechart sum(Confirmed) as Total_Confirmed</query>
          <earliest>0</earliest>
          <sampleRatio>1</sampleRatio>
        </search>
        <option name="charting.axisLabelsX.majorLabelStyle.overflowMode">ellipsisNone</option>
        <option name="charting.axisLabelsX.majorLabelStyle.rotation">0</option>
        <option name="charting.axisTitleX.visibility">visible</option>
        <option name="charting.axisTitleY.visibility">visible</option>
        <option name="charting.axisTitleY2.visibility">visible</option>
        <option name="charting.axisX.abbreviation">none</option>
        <option name="charting.axisX.scale">linear</option>
        <option name="charting.axisY.abbreviation">none</option>
        <option name="charting.axisY.scale">linear</option>
        <option name="charting.axisY2.abbreviation">none</option>
        <option name="charting.axisY2.enabled">0</option>
        <option name="charting.axisY2.scale">inherit</option>
        <option name="charting.chart">column</option>
        <option name="charting.chart.bubbleMaximumSize">50</option>
        <option name="charting.chart.bubbleMinimumSize">10</option>
        <option name="charting.chart.bubbleSizeBy">area</option>
        <option name="charting.chart.nullValueMode">gaps</option>
        <option name="charting.chart.showDataLabels">none</option>
        <option name="charting.chart.sliceCollapsingThreshold">0.01</option>
        <option name="charting.chart.stackMode">default</option>
        <option name="charting.chart.style">shiny</option>
        <option name="charting.drilldown">none</option>
        <option name="charting.layout.splitSeries">0</option>
        <option name="charting.layout.splitSeries.allowIndependentYRanges">0</option>
        <option name="charting.legend.labelStyle.overflowMode">ellipsisMiddle</option>
        <option name="charting.legend.mode">standard</option>
        <option name="charting.legend.placement">right</option>
        <option name="charting.lineWidth">2</option>
        <option name="trellis.enabled">0</option>
        <option name="trellis.scales.shared">1</option>
        <option name="trellis.size">medium</option>
      </chart>
    </panel>
  </row>
  <row>
    <panel>
      <title>Total Deaths</title>
      <single>
        <title>Total number of Deaths</title>
        <search>
          <query>index="corona" source="2019_nCoV_20200121_20200127.csv" Country_Region = "$country$" | stats sum(Death) as Total_Deaths</query>
          <earliest>0</earliest>
          <sampleRatio>1</sampleRatio>
        </search>
        <option name="colorBy">value</option>
        <option name="colorMode">none</option>
        <option name="drilldown">none</option>
        <option name="numberPrecision">0</option>
        <option name="rangeColors">["0x53a051", "0x0877a6", "0xf8be34", "0xf1813f", "0xdc4e41"]</option>
        <option name="rangeValues">[0,30,70,100]</option>
        <option name="showSparkline">1</option>
        <option name="showTrendIndicator">1</option>
        <option name="trellis.enabled">0</option>
        <option name="trellis.scales.shared">1</option>
        <option name="trellis.size">medium</option>
        <option name="trendColorInterpretation">standard</option>
        <option name="trendDisplayMode">absolute</option>
        <option name="unitPosition">after</option>
        <option name="useColors">0</option>
        <option name="useThousandSeparators">1</option>
      </single>
    </panel>
    <panel>
      <title>Total number of Deaths over a period of time</title>
      <chart>
        <search>
          <query>index="corona" source="2019_nCoV_20200121_20200127.csv" Country_Region = "$country$" | timechart sum(Death) as Total_Deaths</query>
          <earliest>0</earliest>
          <sampleRatio>1</sampleRatio>
        </search>
        <option name="charting.axisLabelsX.majorLabelStyle.overflowMode">ellipsisNone</option>
        <option name="charting.axisLabelsX.majorLabelStyle.rotation">0</option>
        <option name="charting.axisTitleX.visibility">visible</option>
        <option name="charting.axisTitleY.visibility">visible</option>
        <option name="charting.axisTitleY2.visibility">visible</option>
        <option name="charting.axisX.abbreviation">none</option>
        <option name="charting.axisX.scale">linear</option>
        <option name="charting.axisY.abbreviation">none</option>
        <option name="charting.axisY.scale">linear</option>
        <option name="charting.axisY2.abbreviation">none</option>
        <option name="charting.axisY2.enabled">0</option>
        <option name="charting.axisY2.scale">inherit</option>
        <option name="charting.chart">line</option>
        <option name="charting.chart.bubbleMaximumSize">50</option>
        <option name="charting.chart.bubbleMinimumSize">10</option>
        <option name="charting.chart.bubbleSizeBy">area</option>
        <option name="charting.chart.nullValueMode">gaps</option>
        <option name="charting.chart.showDataLabels">none</option>
        <option name="charting.chart.sliceCollapsingThreshold">0.01</option>
        <option name="charting.chart.stackMode">default</option>
        <option name="charting.chart.style">shiny</option>
        <option name="charting.drilldown">none</option>
        <option name="charting.layout.splitSeries">0</option>
        <option name="charting.layout.splitSeries.allowIndependentYRanges">0</option>
        <option name="charting.legend.labelStyle.overflowMode">ellipsisMiddle</option>
        <option name="charting.legend.mode">standard</option>
        <option name="charting.legend.placement">right</option>
        <option name="charting.lineWidth">2</option>
        <option name="trellis.enabled">0</option>
        <option name="trellis.scales.shared">1</option>
        <option name="trellis.size">medium</option>
      </chart>
    </panel>
  </row>
</form>
