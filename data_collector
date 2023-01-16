from selenium import webdriver
from selenium.webdriver.common.by import By
from bs4 import BeautifulSoup
import time
import csv

def save_table_data(table_data, file_name):
  """
  Save the table data to a CSV file.

  Parameters:
  table_data (list): The table data to be saved.
  file_name (str): The name of the file to save the data to.
  """
  import csv

  # Get the column names from the first row of the table data
  column_names = list(table_data[0].keys())

  # Open the file for writing in text mode
  with open(file_name, 'w') as csv_file:
    # Create a CSV writer object
    writer = csv.DictWriter(csv_file, fieldnames=column_names)

    # Write the column names as the first row
    writer.writeheader()

    # Write the data to the CSV file
    for row in table_data:
      writer.writerow(row)

def four_factors_home():
  # Set up a webdriver instance using the Chrome browser
  driver = webdriver.Chrome()

  # Navigate to the staking page
  driver.get('https://www.nba.com/stats/teams/four-factors?Location=Home')

  # Wait for the page to load
  time.sleep(15)

  # Get the fully rendered HTML of the page
  html = driver.page_source

  # Parse the HTML of the staking page and extract the trusted answers
  soup = BeautifulSoup(html, 'html.parser')

  # Find the body element
  second_body_element = soup.find('body')

  # Check if the body element was found
  if second_body_element is not None:
    # Find the div element with the data-reactroot attribute
    div_element = second_body_element.find('div', attrs={'data-reactroot': ''})

    # Check if the div element was found
    if div_element is not None:
      # Find the main element with the stakingLayout_container__WzwO_ class
      main_element = div_element.find('div', class_="Layout_base__6IeUC Layout_withSubNav__ByKRF Layout_justNav__2H4H0")

      # Check if the main element was found
      if main_element is not None:
        # Find the div element with the homeView_container__8zV5Z class
        home_view_element = main_element.find('div', class_="Layout_mainContent__jXliI")

        # Check if the home_view_element element was found
        if home_view_element is not None:
          # Find the div element with the dataFeedsSecured_container__SEadr class
          data_feeds_secured_element = home_view_element.find('div', class_="MaxWidthContainer_mwc__ID5AG")

          # Check if the data_feeds_secured_element element was found
          if data_feeds_secured_element is not None:
            # Find the div element with the nodeOperators_container__op_sL class
            node_operators_element = data_feeds_secured_element.find('section', class_="Block_block__62M07 nba-stats-content-block")

            if node_operators_element is not None:
              next_level = node_operators_element.find('div', class_="Block_blockContent__6iJ_n")

              # Check if the node_operators_element element was found
              if next_level is not None:
                # Find the table element
                table_element = next_level.find('table')

                # Check if the table_element element was found
                if table_element is not None:
                  # Extract the table element into a list of dictionaries
                  table_data = []

                  # Find the thead element
                  thead_element = table_element.find('thead')

                  # Extract the column names from the th elements
                  column_names = [th.get_text().strip() for th in thead_element.find_all('th')]

                  # Find the tbody element
                  tbody_element = table_element.find('tbody')

                  # Iterate over the tr elements
                  for tr_element in tbody_element.find_all('tr'):
                    # Extract the data from the td elements
                    data = [td.get_text().strip() for td in tr_element.find_all('td')]

                    # Create a dictionary with the column names as the keys and the data as the values
                    row_data = dict(zip(column_names, data))

                    # Append the dictionary to the list
                    table_data.append(row_data)
                    print(table_data)

                    # Save the table data to a CSV file
                    try:
                      save_table_data(table_data, 'ff_home.csv')
                    except:
                      print('no csv pa')


def four_factors_away():
  # Set up a webdriver instance using the Chrome browser
  driver = webdriver.Chrome()

  # Navigate to the staking page
  driver.get('https://www.nba.com/stats/teams/four-factors?Location=Road')

  # Wait for the page to load
  time.sleep(15)

  # Get the fully rendered HTML of the page
  html = driver.page_source

  # Parse the HTML of the staking page and extract the trusted answers
  soup = BeautifulSoup(html, 'html.parser')

  # Find the body element
  second_body_element = soup.find('body')

  # Check if the body element was found
  if second_body_element is not None:
    # Find the div element with the data-reactroot attribute
    div_element = second_body_element.find('div', attrs={'data-reactroot': ''})

    # Check if the div element was found
    if div_element is not None:
      # Find the main element with the stakingLayout_container__WzwO_ class
      main_element = div_element.find('div', class_="Layout_base__6IeUC Layout_withSubNav__ByKRF Layout_justNav__2H4H0")

      # Check if the main element was found
      if main_element is not None:
        # Find the div element with the homeView_container__8zV5Z class
        home_view_element = main_element.find('div', class_="Layout_mainContent__jXliI")

        # Check if the home_view_element element was found
        if home_view_element is not None:
          # Find the div element with the dataFeedsSecured_container__SEadr class
          data_feeds_secured_element = home_view_element.find('div', class_="MaxWidthContainer_mwc__ID5AG")

          # Check if the data_feeds_secured_element element was found
          if data_feeds_secured_element is not None:
            # Find the div element with the nodeOperators_container__op_sL class
            node_operators_element = data_feeds_secured_element.find('section',
                                                                     class_="Block_block__62M07 nba-stats-content-block")

            if node_operators_element is not None:
              next_level = node_operators_element.find('div', class_="Block_blockContent__6iJ_n")

              # Check if the node_operators_element element was found
              if next_level is not None:
                # Find the table element
                table_element = next_level.find('table')

                # Check if the table_element element was found
                if table_element is not None:
                  # Extract the table element into a list of dictionaries
                  table_data = []

                  # Find the thead element
                  thead_element = table_element.find('thead')

                  # Extract the column names from the th elements
                  column_names = [th.get_text().strip() for th in thead_element.find_all('th')]

                  # Find the tbody element
                  tbody_element = table_element.find('tbody')

                  # Iterate over the tr elements
                  for tr_element in tbody_element.find_all('tr'):
                    # Extract the data from the td elements
                    data = [td.get_text().strip() for td in tr_element.find_all('td')]

                    # Create a dictionary with the column names as the keys and the data as the values
                    row_data = dict(zip(column_names, data))

                    # Append the dictionary to the list
                    table_data.append(row_data)
                    print(table_data)

                    # Save the table data to a CSV file
                    try:
                      save_table_data(table_data, 'ff_away.csv')
                    except:
                      print('no csv pa')




def game_history():
  # Set up a webdriver instance using the Chrome browser
  driver = webdriver.Chrome()

  # Set the start and end years for the game data to collect
  start_year = 2022 - 10
  end_year = 2022

  # Create an empty list to store the game data
  game_data = []

  # Loop through each year in the range
  for year in range(start_year, end_year + 1):
    # Navigate to the game log page for the current year
    driver.get(f'https://www.nba.com/teams/gamelog?Season={year}-{year+1}&SeasonType=Regular%20Season')

    # Wait for the page to load
    time.sleep(15)

    # Get the fully rendered HTML of the page
    html = driver.page_source

    # Parse the HTML and extract the game data
    soup = BeautifulSoup(html, 'html.parser')
    table_element = soup.find('table')

    # Check if the table element was found
    if table_element is not None:
      # Extract the data from the table element
      for tr_element in table_element.find_all('tr'):
        # Extract the data from the td elements
        data = [td.get_text().strip() for td in tr_element.find_all('td')]

        # Create a dictionary with the column names as the keys and the data as the values
        row_data = dict(zip(column_names, data))

        # Append the dictionary to the list
        game_data.append(row_data)

  # Close the webdriver instance
  driver.close()

  # Save the game data to a CSV file
  with open('game_data.csv', 'w', newline='') as csvfile:
    writer = csv.DictWriter(csvfile, fieldnames=column_names)
    writer.writeheader()
    for row in game_data:
      writer.writerow(row)

  # Close the webdriver
  driver.close()


def score_home():
  # Set up a webdriver instance using the Chrome browser
  driver = webdriver.Chrome()

  # Navigate to the staking page
  driver.get('https://www.nba.com/stats/teams/traditional?Location=Home')

  # Wait for the page to load
  time.sleep(15)

  # Get the fully rendered HTML of the page
  html = driver.page_source

  # Parse the HTML of the staking page and extract the trusted answers
  soup = BeautifulSoup(html, 'html.parser')

  # Find the body element
  second_body_element = soup.find('body')

  # Check if the body element was found
  if second_body_element is not None:
    # Find the div element with the data-reactroot attribute
    div_element = second_body_element.find('div', attrs={'data-reactroot': ''})

    # Check if the div element was found
    if div_element is not None:
      # Find the main element with the stakingLayout_container__WzwO_ class
      main_element = div_element.find('div', class_="Layout_base__6IeUC Layout_withSubNav__ByKRF Layout_justNav__2H4H0")

      # Check if the main element was found
      if main_element is not None:
        # Find the div element with the homeView_container__8zV5Z class
        home_view_element = main_element.find('div', class_="Layout_mainContent__jXliI")

        # Check if the home_view_element element was found
        if home_view_element is not None:
          # Find the div element with the dataFeedsSecured_container__SEadr class
          data_feeds_secured_element = home_view_element.find('div', class_="MaxWidthContainer_mwc__ID5AG")

          # Check if the data_feeds_secured_element element was found
          if data_feeds_secured_element is not None:
            # Find the div element with the nodeOperators_container__op_sL class
            node_operators_element = data_feeds_secured_element.find('section', class_="Block_block__62M07 nba-stats-content-block")

            if node_operators_element is not None:
              next_level = node_operators_element.find('div', class_="Block_blockContent__6iJ_n")

              # Check if the node_operators_element element was found
              if next_level is not None:
                # Find the table element
                table_element = next_level.find('table')

                # Check if the table_element element was found
                if table_element is not None:
                  # Extract the table element into a list of dictionaries
                  table_data = []

                  # Find the thead element
                  thead_element = table_element.find('thead')

                  # Extract the column names from the th elements
                  column_names = [th.get_text().strip() for th in thead_element.find_all('th')]

                  # Find the tbody element
                  tbody_element = table_element.find('tbody')

                  # Iterate over the tr elements
                  for tr_element in tbody_element.find_all('tr'):
                    # Extract the data from the td elements
                    data = [td.get_text().strip() for td in tr_element.find_all('td')]

                    # Create a dictionary with the column names as the keys and the data as the values
                    row_data = dict(zip(column_names, data))

                    # Append the dictionary to the list
                    table_data.append(row_data)
                    print(table_data)

                    # Save the table data to a CSV file
                    try:
                      save_table_data(table_data, 'score_home.csv')
                    except:
                      print('no csv pa')

def score_away():
  # Set up a webdriver instance using the Chrome browser
  driver = webdriver.Chrome()

  # Navigate to the staking page
  driver.get('https://www.nba.com/stats/teams/traditional?Location=Road')

  # Wait for the page to load
  time.sleep(15)

  # Get the fully rendered HTML of the page
  html = driver.page_source

  # Parse the HTML of the staking page and extract the trusted answers
  soup = BeautifulSoup(html, 'html.parser')

  # Find the body element
  second_body_element = soup.find('body')

  # Check if the body element was found
  if second_body_element is not None:
    # Find the div element with the data-reactroot attribute
    div_element = second_body_element.find('div', attrs={'data-reactroot': ''})

    # Check if the div element was found
    if div_element is not None:
      # Find the main element with the stakingLayout_container__WzwO_ class
      main_element = div_element.find('div', class_="Layout_base__6IeUC Layout_withSubNav__ByKRF Layout_justNav__2H4H0")

      # Check if the main element was found
      if main_element is not None:
        # Find the div element with the homeView_container__8zV5Z class
        home_view_element = main_element.find('div', class_="Layout_mainContent__jXliI")

        # Check if the home_view_element element was found
        if home_view_element is not None:
          # Find the div element with the dataFeedsSecured_container__SEadr class
          data_feeds_secured_element = home_view_element.find('div', class_="MaxWidthContainer_mwc__ID5AG")

          # Check if the data_feeds_secured_element element was found
          if data_feeds_secured_element is not None:
            # Find the div element with the nodeOperators_container__op_sL class
            node_operators_element = data_feeds_secured_element.find('section', class_="Block_block__62M07 nba-stats-content-block")

            if node_operators_element is not None:
              next_level = node_operators_element.find('div', class_="Block_blockContent__6iJ_n")

              # Check if the node_operators_element element was found
              if next_level is not None:
                # Find the table element
                table_element = next_level.find('table')

                # Check if the table_element element was found
                if table_element is not None:
                  # Extract the table element into a list of dictionaries
                  table_data = []

                  # Find the thead element
                  thead_element = table_element.find('thead')

                  # Extract the column names from the th elements
                  column_names = [th.get_text().strip() for th in thead_element.find_all('th')]

                  # Find the tbody element
                  tbody_element = table_element.find('tbody')

                  # Iterate over the tr elements
                  for tr_element in tbody_element.find_all('tr'):
                    # Extract the data from the td elements
                    data = [td.get_text().strip() for td in tr_element.find_all('td')]

                    # Create a dictionary with the column names as the keys and the data as the values
                    row_data = dict(zip(column_names, data))

                    # Append the dictionary to the list
                    table_data.append(row_data)
                    print(table_data)

                    # Save the table data to a CSV file
                    try:
                      save_table_data(table_data, 'score_away.csv')
                    except:
                      print('no csv pa')

def advanced_home():
  # Set up a webdriver instance using the Chrome browser
  driver = webdriver.Chrome()

  # Navigate to the staking page
  driver.get('https://www.nba.com/stats/teams/advanced?Location=Home')

  # Wait for the page to load
  time.sleep(15)

  # Get the fully rendered HTML of the page
  html = driver.page_source

  # Parse the HTML of the staking page and extract the trusted answers
  soup = BeautifulSoup(html, 'html.parser')

  # Find the body element
  second_body_element = soup.find('body')

  # Check if the body element was found
  if second_body_element is not None:
    # Find the div element with the data-reactroot attribute
    div_element = second_body_element.find('div', attrs={'data-reactroot': ''})

    # Check if the div element was found
    if div_element is not None:
      # Find the main element with the stakingLayout_container__WzwO_ class
      main_element = div_element.find('div', class_="Layout_base__6IeUC Layout_withSubNav__ByKRF Layout_justNav__2H4H0")

      # Check if the main element was found
      if main_element is not None:
        # Find the div element with the homeView_container__8zV5Z class
        home_view_element = main_element.find('div', class_="Layout_mainContent__jXliI")

        # Check if the home_view_element element was found
        if home_view_element is not None:
          # Find the div element with the dataFeedsSecured_container__SEadr class
          data_feeds_secured_element = home_view_element.find('div', class_="MaxWidthContainer_mwc__ID5AG")

          # Check if the data_feeds_secured_element element was found
          if data_feeds_secured_element is not None:
            # Find the div element with the nodeOperators_container__op_sL class
            node_operators_element = data_feeds_secured_element.find('section', class_="Block_block__62M07 nba-stats-content-block")

            if node_operators_element is not None:
              next_level = node_operators_element.find('div', class_="Block_blockContent__6iJ_n")

              # Check if the node_operators_element element was found
              if next_level is not None:
                # Find the table element
                table_element = next_level.find('table')

                # Check if the table_element element was found
                if table_element is not None:
                  # Extract the table element into a list of dictionaries
                  table_data = []

                  # Find the thead element
                  thead_element = table_element.find('thead')

                  # Extract the column names from the th elements
                  column_names = [th.get_text().strip() for th in thead_element.find_all('th')]

                  # Find the tbody element
                  tbody_element = table_element.find('tbody')

                  # Iterate over the tr elements
                  for tr_element in tbody_element.find_all('tr'):
                    # Extract the data from the td elements
                    data = [td.get_text().strip() for td in tr_element.find_all('td')]

                    # Create a dictionary with the column names as the keys and the data as the values
                    row_data = dict(zip(column_names, data))

                    # Append the dictionary to the list
                    table_data.append(row_data)
                    print(table_data)

                    # Save the table data to a CSV file
                    try:
                      save_table_data(table_data, 'advanced_home.csv')
                    except:
                      print('no csv pa')

def advanced_away():
  # Set up a webdriver instance using the Chrome browser
  driver = webdriver.Chrome()

  # Navigate to the staking page
  driver.get('https://www.nba.com/stats/teams/advanced?Location=Road')

  # Wait for the page to load
  time.sleep(15)

  # Get the fully rendered HTML of the page
  html = driver.page_source

  # Parse the HTML of the staking page and extract the trusted answers
  soup = BeautifulSoup(html, 'html.parser')

  # Find the body element
  second_body_element = soup.find('body')

  # Check if the body element was found
  if second_body_element is not None:
    # Find the div element with the data-reactroot attribute
    div_element = second_body_element.find('div', attrs={'data-reactroot': ''})

    # Check if the div element was found
    if div_element is not None:
      # Find the main element with the stakingLayout_container__WzwO_ class
      main_element = div_element.find('div', class_="Layout_base__6IeUC Layout_withSubNav__ByKRF Layout_justNav__2H4H0")

      # Check if the main element was found
      if main_element is not None:
        # Find the div element with the homeView_container__8zV5Z class
        home_view_element = main_element.find('div', class_="Layout_mainContent__jXliI")

        # Check if the home_view_element element was found
        if home_view_element is not None:
          # Find the div element with the dataFeedsSecured_container__SEadr class
          data_feeds_secured_element = home_view_element.find('div', class_="MaxWidthContainer_mwc__ID5AG")

          # Check if the data_feeds_secured_element element was found
          if data_feeds_secured_element is not None:
            # Find the div element with the nodeOperators_container__op_sL class
            node_operators_element = data_feeds_secured_element.find('section', class_="Block_block__62M07 nba-stats-content-block")

            if node_operators_element is not None:
              next_level = node_operators_element.find('div', class_="Block_blockContent__6iJ_n")

              # Check if the node_operators_element element was found
              if next_level is not None:
                # Find the table element
                table_element = next_level.find('table')

                # Check if the table_element element was found
                if table_element is not None:
                  # Extract the table element into a list of dictionaries
                  table_data = []

                  # Find the thead element
                  thead_element = table_element.find('thead')

                  # Extract the column names from the th elements
                  column_names = [th.get_text().strip() for th in thead_element.find_all('th')]

                  # Find the tbody element
                  tbody_element = table_element.find('tbody')

                  # Iterate over the tr elements
                  for tr_element in tbody_element.find_all('tr'):
                    # Extract the data from the td elements
                    data = [td.get_text().strip() for td in tr_element.find_all('td')]

                    # Create a dictionary with the column names as the keys and the data as the values
                    row_data = dict(zip(column_names, data))

                    # Append the dictionary to the list
                    table_data.append(row_data)
                    print(table_data)

                    # Save the table data to a CSV file
                    try:
                      save_table_data(table_data, 'advanced_away.csv')
                    except:
                      print('no csv pa')


def player(id):
  # Set up a webdriver instance using the Chrome browser
  driver = webdriver.Chrome()

  # Navigate to the staking page
  driver.get(f'https://www.nba.com/stats/player/{id}')

  # Wait for the page to load
  time.sleep(15)

  # Get the fully rendered HTML of the page
  html = driver.page_source

  # Parse the HTML of the staking page and extract the trusted answers
  soup = BeautifulSoup(html, 'html.parser')

  # Find the body element
  second_body_element = soup.find('body')

  # Check if the body element was found
  if second_body_element is not None:
    # Find the div element with the data-reactroot attribute
    div_element = second_body_element.find('div', attrs={'data-reactroot': ''})

    # Check if the div element was found
    if div_element is not None:
      # Find the main element with the stakingLayout_container__WzwO_ class
      main_element = div_element.find('div', class_="Layout_base__6IeUC Layout_withSubNav__ByKRF Layout_justNav__2H4H0")

      # Check if the main element was found
      if main_element is not None:
        # Find the div element with the homeView_container__8zV5Z class
        home_view_element = main_element.find('div', class_="Layout_mainContent__jXliI")

        # Check if the home_view_element element was found
        if home_view_element is not None:
          # Find the div element with the dataFeedsSecured_container__SEadr class
          data_feeds_secured_element = home_view_element.find('div', class_="MaxWidthContainer_mwc__ID5AG")

          # Check if the data_feeds_secured_element element was found
          if data_feeds_secured_element is not None:
            # Find the div element with the nodeOperators_container__op_sL class
            node_operators_element = data_feeds_secured_element.find('section', class_="Block_block__62M07 nba-stats-content-block")

            if node_operators_element is not None:
              next_level = node_operators_element.find('div', class_="Block_blockContent__6iJ_n")

              # Check if the node_operators_element element was found
              if next_level is not None:
                # Find the table element
                table_element = next_level.find('table')

                # Check if the table_element element was found
                if table_element is not None:
                  # Extract the table element into a list of dictionaries
                  table_data = []

                  # Find the thead element
                  thead_element = table_element.find('thead')

                  # Extract the column names from the th elements
                  column_names = [th.get_text().strip() for th in thead_element.find_all('th')]

                  # Find the tbody element
                  tbody_element = table_element.find('tbody')

                  # Iterate over the tr elements
                  for tr_element in tbody_element.find_all('tr'):
                    # Extract the data from the td elements
                    data = [td.get_text().strip() for td in tr_element.find_all('td')]

                    # Create a dictionary with the column names as the keys and the data as the values
                    row_data = dict(zip(column_names, data))

                    # Append the dictionary to the list
                    table_data.append(row_data)
                    print(table_data)

                    # Save the table data to a CSV file
                    try:
                      save_table_data(table_data, 'player.csv')
                    except:
                      print('no csv pa')

four_factors_away()
four_factors_home()
advanced_away()
advanced_home()
score_away()
score_home()
