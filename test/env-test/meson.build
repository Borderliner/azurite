sfml_code = '''

#include <cstdlib>
#include <memory>

#include <SFML/Graphics.hpp>

int main(int argc, char* argv[]) {
    auto window = std::make_shared<sf::RenderWindow>(sf::VideoMode::getDesktopMode(), "Platformer C++");

    while (window->isOpen()) {
        sf::Event event;

        while (window->pollEvent(event)) {
            if (event.type == sf::Event::Closed) {
                window->close();
            }
        }

        window->clear(sf::Color::Black);
        // Draw
        window->display();

    }

    std::exit(EXIT_SUCCESS);
}

'''

compiler = meson.get_compiler('cpp')

result_compiler = compiler.compiles(sfml_code, name: 'SFML sample code compiles')

if result_compiler == false
    error('Cannot compile SFML sample code.')
endif
